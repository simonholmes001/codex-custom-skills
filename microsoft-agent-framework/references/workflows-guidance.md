# Workflows Guidance (C#-oriented)

Use this guide when building deterministic, graph-driven orchestration with Microsoft Agent Framework.

Evidence level: `Partial` for some advanced pages; `Derived` for reliability/control recommendations.

## When to Use Workflows

- Use workflows when execution order, branching, and recovery must be explicit and repeatable.
- Keep agent reasoning inside nodes; keep control flow in graph definitions.
- Prefer workflow-first for regulated or high-audit scenarios.

## Core Building Blocks

- Executors: runtime for processing workflow nodes and transitions.
- Edges: define valid transitions and routing conditions.
- Events: trigger transitions, external signals, and lifecycle hooks.
- State: shared execution context carried across nodes.

## State and Checkpoints

- Model state as versioned contracts, not ad-hoc dictionaries.
- Use checkpoints for resumability and crash recovery.
- Define checkpoint policy:
1. Frequency (every node, critical nodes, timed).
2. Storage backend and retention.
3. Replay/recovery procedure.
- Make state updates idempotent where possible to reduce replay risk.

```csharp
// Sketch: checkpoint-friendly node update pattern.
public sealed record WorkflowState(string RequestId, string? Result, int Step);

public static WorkflowState Advance(WorkflowState s, string result) =>
    s with { Result = result, Step = s.Step + 1 };
```

## Agents in Workflows

- Embed agents as node executors for reasoning-heavy steps.
- Bound agent node behavior with iteration/tool limits and timeout controls.
- Normalize agent outputs into typed state updates before routing downstream.

## Human-in-the-Loop (HITL)

- Insert approval gates on high-risk transitions and side-effecting actions.
- Persist approval context (requested action, evidence, approver decision).
- Define deny/timeout branches explicitly; never leave approval outcomes implicit.

## Declarative Workflows

- Use declarative workflow specs for reviewability and change control.
- Validate declarative files in CI (schema + semantic checks).
- Keep runtime overrides minimal and auditable.

## Observability and Visualization

- Emit OpenTelemetry spans per node execution, transition, and retry.
- Track graph-level metrics: node latency, failure rate, retries, stalled runs.
- Use visualization outputs for design review and incident analysis.
- Version diagrams with workflow specs to avoid drift.

## Workflows as Agents

- Wrap workflows as agent-callable capabilities when you need deterministic subroutines from agent orchestration.
- Expose narrow input/output contracts and preserve checkpoint/trace context across the boundary.

## Orchestration Pattern Mapping

- Sequential: ordered stages with strict dependencies.
- Concurrent: parallel branches with join/merge logic.
- Handoff: delegated responsibility transfer between specialists.
- Group chat: collaborative multi-agent deliberation with shared context.

Choose the minimal orchestration pattern that satisfies quality, latency, and governance requirements.

## Reliability Controls

- Add retry policy by failure class (transient vs terminal).
- Add dead-letter handling for unrecoverable nodes.
- Add global execution timeout and stall detection.
- Test replay/restart scenarios before production rollout.
