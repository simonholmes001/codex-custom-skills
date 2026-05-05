---
name: microsoft-agent-framework-mcp
description: Integrate Microsoft Agent Framework agents with MCP tool servers safely and reliably. Use when Codex needs to design MCP-enabled agent architectures, configure tool registration and routing, enforce governance controls (allowlists, approvals, least privilege), troubleshoot tool-call failures, or define observability/audit patterns for agent-to-tool execution.
metadata:
  category: agents-mcp
  subdomain: agent-framework-mcp
  owner: custom
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
