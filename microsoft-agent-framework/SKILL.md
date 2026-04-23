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
3. Select orchestration pattern by coordination needs (sequential, concurrent, group chat, handoff, magentic).
4. Define core building blocks: model client, agent/session state, tools, memory/context providers, middleware, telemetry.
5. Add production controls: auth model, approvals, observability, retry/durability, and governance boundaries.
6. Validate with realistic scenarios and fallback paths.

## Load References Selectively

- For authoritative links and canonical docs, read `references/official-docs.md`.
- For framework concepts and architecture boundaries, read `references/framework-overview.md`.
- For orchestration pattern selection, read `references/orchestration-patterns.md`.
- For implementation bootstrap in .NET/C#, read `references/csharp-quickstart.md`.
- For production and ecosystem positioning, read `references/maf-production-guidance.md`.

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
