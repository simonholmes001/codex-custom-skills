---
name: microsoft-agent-framework
description: Build, review, and troubleshoot agentic applications with Microsoft Agent Framework across .NET and Python. Use when Codex needs to design agent/workflow architecture, choose orchestration patterns, implement or migrate Microsoft Agent Framework code, configure providers/tools/middleware/memory, or apply production readiness practices (observability, approvals, security, durability).
metadata:
  category: agents-mcp
  subdomain: agent-framework
  owner: custom
---

# Microsoft Agent Framework

## Overview

Use this skill to design and implement Microsoft Agent Framework (MAF) solutions with an explicit split between:

- Agent orchestration: LLM-driven, adaptive reasoning and tool use.
- Workflow orchestration: deterministic graph execution with explicit control flow.

This skill is source-grounded. For substantive guidance, perform a full source pass before recommendations.

## Mandatory Source Pass

Before architecture recommendations, migration plans, production hardening guidance, or implementation advice:

1. Read `references/official-docs.md` for canonical links and metadata.
2. Read `references/source-pass-protocol.md` and follow it end-to-end.
3. Complete coverage using `references/source-coverage-matrix.md`.
4. Only then load domain-specific references for synthesis.

If a task is tiny (for example one API symbol lookup), you may do a scoped source pass for only the relevant section in the coverage matrix. State that scope explicitly.

## Workflow

1. Clarify runtime and scope: .NET or Python, local or Azure-hosted, single-agent or multi-agent.
2. Perform source pass and mark coverage by topic.
3. Choose lowest viable complexity: direct model call, single agent with tools, or multi-agent orchestration.
4. Select orchestration pattern by coordination needs (sequential, concurrent, group chat, handoff, magnetic).
5. Define core building blocks: model client, agent/session state, tools, memory/context providers, middleware, telemetry.
6. Add production controls: auth model, approvals, observability, retry/durability, and governance boundaries.
7. Validate with realistic scenarios, fallback paths, and rollback criteria.

## Load References

After mandatory source pass, load targeted references:

- Canonical links and validation metadata: `references/official-docs.md`
- Full-pass execution protocol: `references/source-pass-protocol.md`
- Coverage tracker by topic: `references/source-coverage-matrix.md`
- Framework concepts and boundaries: `references/framework-overview.md`
- Orchestration pattern selection: `references/orchestration-patterns.md`
- C# bootstrap: `references/csharp-quickstart.md`
- Advanced agent capabilities: `references/agents-advanced.md`
- Tool selection and approvals: `references/tools-guidance.md`
- Sessions/context/storage/compaction: `references/conversations-memory.md`
- Middleware scoping/termination: `references/middleware-guidance.md`
- Provider selection/setup constraints: `references/providers-guidance.md`
- Workflow graph/state/checkpoints/observability: `references/workflows-guidance.md`
- Advanced workflow execution patterns: `references/workflows-advanced.md`
- A2A hosting and integration: `references/a2a-hosting-integration.md`
- .NET API namespace orientation: `references/dotnet-api-surface.md`
- Staged architecture evolution: `references/journey-playbook.md`
- Production hardening and governance: `references/maf-production-guidance.md`

## Routing Matrix

- "Need canonical docs and current path?" -> `references/official-docs.md`
- "Need full evidence-backed guidance?" -> `references/source-pass-protocol.md`, `references/source-coverage-matrix.md`
- "Single-agent vs workflow architecture?" -> `references/framework-overview.md`, `references/orchestration-patterns.md`
- "How to start quickly in C#?" -> `references/csharp-quickstart.md`
- "Tools/function tools/approvals/MCP?" -> `references/tools-guidance.md`
- "Sessions/context providers/storage/compaction?" -> `references/conversations-memory.md`
- "Middleware and termination limits?" -> `references/middleware-guidance.md`
- "Provider selection?" -> `references/providers-guidance.md`
- "Workflow graph/checkpoints/observability?" -> `references/workflows-guidance.md`
- "Advanced workflow execution modes/sub-workflows?" -> `references/workflows-advanced.md`
- "Host/integrate A2A endpoints?" -> `references/a2a-hosting-integration.md`
- "Need class-level .NET API details?" -> `references/dotnet-api-surface.md`
- "Following journey sequence?" -> `references/journey-playbook.md`
- "Production hardening checklist?" -> `references/maf-production-guidance.md`

## Design Rules

1. Prefer the simplest architecture that satisfies quality attributes.
2. Use single-agent plus tools before multi-agent orchestration unless coordination demands otherwise.
3. Use workflows for deterministic paths and agents for open-ended reasoning.
4. Enforce tool-call bounds, iteration limits, and stall detection.
5. Make trust boundaries explicit for each provider, tool, and remote agent.
6. Treat memory as a deliberate design dimension (scope, persistence, retention, compaction).
7. Instrument OpenTelemetry from the first production candidate.
8. Add human approval gates for sensitive or irreversible operations.
9. Separate documented facts from derived guidance; label assumptions.
10. Record major choices as ADRs with alternatives and disqualifiers.

## Output Contract

For architecture/review/implementation answers:

1. `Context and Scope`
2. `Source Coverage Summary` (what was read, what was not, and why)
3. `Pattern Decision` (problem, options, selected approach, tradeoffs)
4. `Implementation Plan` (.NET/Python where relevant)
5. `Operations and Safety Controls` (auth, telemetry, approvals, resilience)
6. `Validation Plan` (tests, rollout gates, rollback criteria)
7. `Assumptions and Open Risks`

## Delivery Templates

Use when helpful:

- `Pattern Decision`
- `Implementation Plan`
- `Ops Checklist`
- `Source Coverage Report`

## Quick vs Deep Mode Policy

Use this decision policy to balance depth, cost, and response speed:

### Quick Mode (default)

Use when the request is narrow, exploratory, or low-risk.

1. Read `SKILL.md` and `references/cross-skill-standards.md`.
2. Read only the minimum task-relevant references for the scoped request.
3. In the response, state:
- references read
- references intentionally not read
- confidence level (`Verified`, `Derived`, `Assumption`)

### Deep Mode (mandatory full source pass)

Switch to Deep Mode when any of the following is true:

1. The request drives production, go-live, or high-blast-radius decisions.
2. The request has security, compliance, legal, or financial risk implications.
3. The request asks for comprehensive, authoritative, or sign-off-quality guidance.
4. The request includes major architecture or migration commitments.
5. Quick Mode leaves material uncertainty, conflicting evidence, or low confidence.

In Deep Mode, execute the skill's fullest available source pass workflow for its domain before final recommendations.

### Escalation Rule

Start in Quick Mode unless high-stakes triggers are already explicit. Escalate to Deep Mode immediately when uncertainty remains material.

## Cross-Skill Standards

Read and apply `references/cross-skill-standards.md` for:

- Evidence quality rubric (`Verified`, `Derived`, `Assumption`)
- Context-budget/loading policy
- Anti-pattern and handoff rules
- Source freshness policy
- Minimum output additions for non-trivial responses
