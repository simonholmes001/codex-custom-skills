---
name: microsoft-agent-framework-mcp
description: Integrate Microsoft Agent Framework agents with MCP tool servers safely and reliably. Use when Codex needs to design MCP-enabled agent architectures, configure tool registration and routing, enforce governance controls (allowlists, approvals, least privilege), troubleshoot tool-call failures, or define observability/audit patterns for agent-to-tool execution.
---

# Microsoft Agent Framework MCP

## Overview

Use this skill to design and implement MAF solutions that call external capabilities through MCP servers with explicit safety, reliability, and governance controls.

## Workflow

1. Define scope and trust boundary: which MCP servers, tools, and data domains are in play.
2. Choose invocation model: direct tool call, mediated planner-agent flow, or manager/worker delegation.
3. Define tool contracts: input/output schema, timeout, retry budget, and idempotency assumptions.
4. Enforce governance: allowlisted tools, approval gates, scoped credentials, and redaction rules.
5. Implement telemetry: per-call tracing, latency/error metrics, and audit logs.
6. Validate failure paths: MCP unavailability, schema drift, partial responses, and rollback behavior.

## Load References Selectively

- For authoritative docs and source links, read `references/official-docs.md`.
- For architecture and trust boundaries, read `references/maf-mcp-architecture.md`.
- For implementation patterns and pseudo-flow, read `references/integration-patterns.md`.
- For governance and safety controls, read `references/governance-controls.md`.
- For troubleshooting and operational checks, read `references/ops-troubleshooting.md`.

## Design Rules

Apply these rules consistently:
1. Default-deny tool access; explicitly allow only required MCP tools.
2. Keep agent prompts/tool schemas versioned and auditable.
3. Put deterministic guardrails around autonomous tool loops.
4. Require approval for sensitive mutating operations.
5. Separate read-only and write-capable tools by policy and identity.
6. Treat MCP outputs as untrusted input until validated.
7. Emit OpenTelemetry spans for every tool call edge.
8. Define fallback behavior when an MCP dependency is degraded.

## Output Contract

For each architecture or implementation answer:
1. State MCP topology and trust boundaries.
2. Explain selected integration pattern and tradeoffs.
3. List concrete implementation steps (registration, routing, retries, auth).
4. Include governance controls (approvals, allowlists, RBAC, audit).
5. Provide validation checks and rollback/fallback strategy.

## Delivery Templates

When useful, structure output as:
- `MCP Integration Decision` (context, options, selected pattern)
- `Control Matrix` (risk -> control -> telemetry)
- `Runbook` (failure symptom -> check -> remediation)
