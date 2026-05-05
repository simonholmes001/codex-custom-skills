---
name: gh-project-ops
description: Use this skill for GitHub Project board manipulation. Includes mandatory authentication and scope preflight steps before running gh project commands.
metadata:
  category: github
  subdomain: github-operations
  owner: custom
---

# gh-project-ops

Use this skill for any GitHub Project board manipulation.

## Mandatory preflight (always run first)

1) Check auth:
`gh auth status -h github.com`

2) If not logged in / token invalid:
`gh auth login -h github.com`

3) Check project access:
`gh project list --owner @me`

4) If error says missing scopes like `[read:project]` or `[project]`:
`gh auth refresh -h github.com -s read:project -s project`

5) Re-run:
`gh project list --owner @me`

Only proceed with `gh project ...` commands after step 5 succeeds.

## Rule

Do not guess alternate auth commands.
Preferred commands are exactly:
- `gh auth login -h github.com`
- `gh auth refresh -h github.com -s read:project -s project`

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
