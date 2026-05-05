---
name: github-mcp
description: Operate GitHub repositories through an MCP server for issue triage, pull request workflows, repository inspection, and metadata updates. Use when Codex needs to search repositories, read or update issues and PRs, inspect files and commits, manage labels and milestones, or automate GitHub coordination tasks through MCP instead of direct git or manual UI steps.
metadata:
  category: github
  subdomain: github-operations
  owner: custom
---

# GitHub MCP

## Overview

Use MCP-backed GitHub operations to execute repeatable repo workflows with explicit safety boundaries. Start with read actions, then perform write actions only after confirming scope and impact.

## Workflow

1. Collect owner, repo, branch/PR/issue identifiers, and expected outcome.
2. Discover relevant MCP capabilities for the requested operation.
3. Perform read operations first to confirm current state.
4. Apply scoped write operation only after validating target and side effects.
5. Return clear action summary, links/IDs, and follow-up checks.

## Load References Selectively

- For end-to-end task playbooks, read `references/workflows.md`.
- For mutation safety and approval boundaries, read `references/safety.md`.
- For authoritative and current MCP/GitHub MCP guidance, read `references/official-docs.md`.

## Task Categories

1. Issues and triage
- Search/filter issues by label, assignee, milestone, or state.
- Create/update issues with concise problem statements and acceptance criteria.
- Normalize labels and ownership for backlog hygiene.

2. Pull request workflows
- Inspect PR state, checks, reviewers, and mergeability.
- Add review comments, request reviewers, and update PR metadata.
- Prepare merge recommendations with explicit risk callouts.

3. Repository inspection
- Inspect branch, file, commit, and release context through MCP reads.
- Build change summaries from commit and PR metadata.

## Safety Rules

Always enforce:
1. Confirm target repo and object ID before writes.
2. Avoid destructive or irreversible operations without explicit user approval.
3. Avoid broad bulk edits unless user requests bulk mode.
4. Summarize what changed, where, and why.
5. Surface permission failures and required access plainly.

## Output Contract

For each request:
1. State planned MCP operations before execution when writes are involved.
2. Report artifacts with repo, object ID, and resulting state.
3. Include unresolved assumptions and next suggested action.

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
