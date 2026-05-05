---
name: mcp-servers
description: Design, implement, and troubleshoot Model Context Protocol (MCP) server integrations across local and remote runtimes. Use when Codex needs to choose MCP server/client topology, configure transport and authentication, connect tools safely, evaluate server catalogs, or apply governance and operational controls for production MCP usage.
metadata:
  category: agents-mcp
  subdomain: mcp-integration
  owner: custom
---

# MCP Servers

## Overview

Use this skill to build reliable MCP server integrations and apply consistent security, observability, and operational practices.

## Workflow

1. Clarify topology: local vs remote MCP server, single vs multi-server integration.
2. Identify capability requirements: tools, data sources, workflows, and required trust boundaries.
3. Choose server sources: first-party, community, or custom-built server.
4. Define connection model: transport, auth, and permission scope.
5. Add runtime controls: allowlists, timeout/retry limits, and output validation.
6. Validate operations: health, telemetry, error handling, and rollback path.

## Load References Selectively

- For canonical docs and ecosystem links, read `references/official-docs.md`.
- For MCP core concepts and architecture, read `references/mcp-foundations.md`.
- For server integration patterns and tradeoffs, read `references/server-integration-patterns.md`.
- For Azure MCP Server specifics, read `references/azure-mcp-server.md`.
- For security and governance guidance, read `references/security-governance.md`.
- For operations and troubleshooting flow, read `references/ops-troubleshooting.md`.

## Design Rules

Apply these rules consistently:
1. Start with least privilege and explicit tool allowlists.
2. Separate read-only and write-capable server access paths.
3. Treat all MCP outputs as untrusted until validated.
4. Set hard limits on retries, call depth, and execution duration.
5. Keep credentials scoped, rotated, and environment-specific.
6. Capture traceability for each tool call edge.
7. Prefer deterministic fallback behavior when servers degrade.
8. Version integration contracts (schemas, tool names, routing rules).

## Output Contract

For each architecture or implementation answer:
1. State the MCP topology and capability mapping.
2. Explain why the chosen integration pattern fits.
3. List concrete setup/configuration steps.
4. Include security/governance controls and audit approach.
5. Provide validation checks and rollback/fallback plan.

## Delivery Templates

When useful, structure output as:
- `MCP Topology Decision` (context, options, selected model)
- `Control Matrix` (risk -> control -> telemetry)
- `Runbook` (symptom -> diagnosis -> remediation)

## Cross-Skill Standards

Read and apply `references/cross-skill-standards.md` for:

- Evidence quality rubric (`Verified`, `Derived`, `Assumption`)
- Context-budget/loading policy
- Anti-pattern and handoff rules
- Source freshness policy
- Minimum output additions for non-trivial responses
