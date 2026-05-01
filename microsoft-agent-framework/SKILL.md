---
name: microsoft-agent-framework
description: Build, review, and troubleshoot agentic applications with Microsoft Agent Framework across .NET and Python. Use when Codex needs to design agent/workflow architecture, choose orchestration patterns, implement or migrate Microsoft Agent Framework code, configure providers/tools/middleware/memory, or apply production readiness practices (observability, approvals, security, durability).
---

# Microsoft Agent Framework

## Overview

Use this skill to plan and implement Microsoft Agent Framework solutions with a clear split between agent orchestration (LLM-driven) and workflow orchestration (deterministic graph execution).

## Workflow

1. Clarify runtime and scope: .NET or Python, local or Azure-hosted, single-agent or multi-agent.
2. Choose the lowest viable complexity: direct model call, single agent with tools, or multi-agent orchestration.
3. Select orchestration pattern by coordination needs (sequential, concurrent, group chat, handoff, magnetic).
4. Define core building blocks: model client, agent/session state, tools, memory/context providers, middleware, telemetry.
5. Add production controls: auth model, approvals, observability, retry/durability, and governance boundaries.
6. Validate with realistic scenarios and fallback paths.

## Load References Selectively

- For authoritative links and canonical docs, read `references/official-docs.md`.
- For framework concepts and architecture boundaries, read `references/framework-overview.md`.
- For orchestration pattern selection, read `references/orchestration-patterns.md`.
- For implementation bootstrap in .NET/C#, read `references/csharp-quickstart.md`.
- For advanced agent capabilities (pipeline, background responses, declarative, RAG, skills, CodeAct, structured outputs, multimodal), read `references/agents-advanced.md`.
- For tool-type selection and approvals (function/code-interpreter/file/web/MCP), read `references/tools-guidance.md`.
- For sessions, context providers, storage, compaction, and conversation lifecycle design, read `references/conversations-memory.md`.
- For middleware implementation and scoping choices, read `references/middleware-guidance.md`.
- For provider selection and provider-specific setup constraints, read `references/providers-guidance.md`.
- For workflow graph design (executors, edges, events, state, checkpoints, orchestration, observability), read `references/workflows-guidance.md`.
- For advanced workflow execution patterns (agent executors, execution modes, resettable executors, sub-workflows), read `references/workflows-advanced.md`.
- For A2A hosting and integration patterns, read `references/a2a-hosting-integration.md`.
- For .NET API namespace orientation and class discovery, read `references/dotnet-api-surface.md`.
- For staged architecture evolution guidance, read `references/journey-playbook.md`.
- For production and ecosystem positioning, read `references/maf-production-guidance.md`.
- When the user asks for onboarding or tutorial flows, prioritize the current `get-started/*` docs over legacy `tutorials/*` links.

## Routing Matrix

Use this quick router for common user asks:

- "How do I start quickly in C#?" -> `references/csharp-quickstart.md`
- "Which docs are canonical for this topic?" -> `references/official-docs.md`
- "Single-agent vs workflow architecture?" -> `references/framework-overview.md`, `references/orchestration-patterns.md`
- "Tools/function tools/approvals/MCP?" -> `references/tools-guidance.md`
- "Sessions/context providers/storage/compaction?" -> `references/conversations-memory.md`
- "Middleware design and termination limits?" -> `references/middleware-guidance.md`
- "Provider selection (OpenAI/Anthropic/Copilot/A2A/custom)?" -> `references/providers-guidance.md`
- "Workflow graph, checkpoints, observability?" -> `references/workflows-guidance.md`
- "Advanced workflow modes/sub-workflows/resettable executors?" -> `references/workflows-advanced.md`
- "Host or integrate A2A endpoints?" -> `references/a2a-hosting-integration.md`
- "Need class-level .NET API details?" -> `references/dotnet-api-surface.md`
- "Following the journey sequence?" -> `references/journey-playbook.md`
- "Production hardening checklist?" -> `references/maf-production-guidance.md`

## Design Rules

Apply these rules consistently:
1. Prefer the simplest architecture that meets the requirement.
2. Use single-agent plus tools as default before moving to multi-agent orchestration.
3. Use workflows for deterministic paths, and agent orchestration for open-ended reasoning.
4. Put tool-call and iteration limits in place to avoid loops.
5. Make security boundaries explicit for each agent and tool.
6. Treat memory as a deliberate design choice (scope, persistence, retention).
7. Add OpenTelemetry instrumentation from the first working version.
8. Include human approval gates for sensitive actions.

## Output Contract

For architecture or implementation answers:
1. State target design in concise bullets.
2. Explain why the selected orchestration pattern fits.
3. List implementation steps by runtime (.NET/Python) where relevant.
4. Include safety/operations controls (auth, telemetry, approvals, rollback).
5. Call out assumptions and unresolved risks.

## Delivery Templates

When useful, structure output as:
- `Pattern Decision` (problem, options, selection, tradeoffs)
- `Implementation Plan` (packages, config, code steps, validation)
- `Ops Checklist` (monitoring, security, reliability, governance)
