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

## Cross-Skill Standards

Read and apply `references/cross-skill-standards.md` for:

- Evidence quality rubric (`Verified`, `Derived`, `Assumption`)
- Context-budget/loading policy
- Anti-pattern and handoff rules
- Source freshness policy
- Minimum output additions for non-trivial responses
