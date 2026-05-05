---
name: azure-mcp
description: Operate Microsoft Azure through an MCP server for resource discovery, diagnostics, and controlled configuration changes. Use when Codex needs to inspect subscriptions and resource groups, review service configuration, troubleshoot platform issues, validate policy posture, or execute scoped Azure operations through MCP tools.
metadata:
  category: azure
  subdomain: operations
  owner: custom
---

# Azure MCP

## Overview

Use MCP-backed Azure operations to inspect and manage cloud resources with clear scope control. Prefer read-first diagnostics, then apply minimal safe changes with verification and rollback.

## Workflow

1. Collect subscription, resource group, region, and service scope.
2. Discover available MCP capabilities for targeted service operations.
3. Perform read and diagnostics checks first.
4. Propose smallest safe change and required prerequisites.
5. Apply change only with explicit user confirmation for write operations.
6. Validate post-change state and report rollback path.

## Load References Selectively

- For common Azure MCP workflows, read `references/workflows.md`.
- For safety model and approvals, read `references/safety.md`.
- For authoritative and current Azure MCP guidance, read `references/official-docs.md`.

## Task Categories

1. Resource inventory and posture
- Enumerate subscriptions, resource groups, and key services in scope.
- Summarize deployment footprint and configuration drift signals.

2. Troubleshooting and diagnostics
- Inspect service health, recent activity, and relevant configuration.
- Correlate symptoms with likely misconfiguration or dependency issues.

3. Controlled operations
- Apply scoped updates (for example tags, settings, or access changes) after confirmation.
- Capture before/after state and validation outputs.

## Safety Rules

Always enforce:
1. Confirm tenant/subscription/resource scope before any mutation.
2. Prefer least-privilege, least-impact changes.
3. Request explicit user approval for writes, especially identity/network/security changes.
4. Define rollback before applying mutation.
5. Report permission boundaries and failures clearly.

## Output Contract

For each request:
1. State scope and MCP operations used.
2. Present findings or change result with resource identifiers.
3. Provide validation checks and rollback guidance.
4. List unresolved assumptions and next action.

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
