# Framework Overview Notes

## What Agent Framework Is

Microsoft Agent Framework is an open-source, multi-language framework for building, orchestrating, and deploying AI agents and multi-agent workflows in .NET and Python.

It combines:
- AutoGen lineage for lightweight agent abstractions and multi-agent patterns.
- Semantic Kernel lineage for enterprise controls such as state management, middleware, and telemetry.
- Workflow orchestration for explicit, graph-based, deterministic control.

## Core Building Blocks

Use these concepts when designing solutions:
- Model clients: chat/responses providers.
- Agents: instruction + tool-enabled runtime units.
- Session/state: conversation and execution continuity.
- Context providers/memory: pluggable short- and long-term context.
- Middleware: interception hooks for policy, logging, validation, and safety.
- MCP and other tool integrations: connect external systems via standard interfaces.

## Agent vs Workflow Decision

Use agent orchestration when:
- Tasks are open-ended or require dynamic reasoning/tool choice.
- You benefit from autonomous planning and adaptation.

Use workflow orchestration when:
- Steps are deterministic and order-dependent.
- You need predictable execution and explicit graph control.

If a deterministic function solves the task, prefer that over introducing an agent.

## Key Operational Themes

- Add OpenTelemetry early for traceability.
- Define retries/timeouts and stall handling for long-running operations.
- Use approvals for sensitive actions.
- Prefer explicit auth boundaries (managed identities, RBAC, scoped credentials).
