---
name: branch-discipline
description: "Enforce strict git hygiene before any code change in repository work: sync local main to origin/main, create a new branch from synced main, create and use a dedicated worktree for that branch, and avoid editing from the primary repository checkout. Use whenever implementing a feature/fix, opening a PR, or addressing review comments."
metadata:
  category: engineering-practice
  subdomain: delivery-quality
  owner: custom
---

# Branch Discipline

## Mandatory Workflow

Run these steps in order before editing code:

1. Confirm current repository state (`git status --short --branch`).
2. Fetch and prune remotes (`git fetch origin --prune`).
3. Switch to `main` and fast-forward only (`git switch main && git merge --ff-only origin/main`).
4. Create a new branch from synced `main`.
5. Create a dedicated worktree for that new branch.
6. Perform all edits, tests, commits, and pushes from that worktree path.

## Hard Rules

- Never implement feature/fix changes directly from the primary repository checkout when a worktree is required.
- Never skip sync of local `main` with `origin/main` before creating a branch.
- Never use `--no-verify`.
- Never merge without explicit user permission.
- Never trigger pipelines manually without explicit user permission.

## Required Operator Confirmation

Before first code edit in a task, explicitly report:

- Synced `main` SHA (local and remote, both values)
- New branch name
- Worktree absolute path

## If Blocked

If a required step fails (permissions, lock, network), stop and report:

1. Which exact step failed
2. The command/error
3. The smallest safe next action

## Completion Checklist

Before final response, verify and report:

1. Work was done from the declared worktree path
2. Branch is not `main`
3. Local `main` remains aligned to `origin/main` (or state why not)

## Cross-Skill Standards

Read and apply `references/cross-skill-standards.md` for:

- Evidence quality rubric (`Verified`, `Derived`, `Assumption`)
- Context-budget/loading policy
- Anti-pattern and handoff rules
- Source freshness policy
- Minimum output additions for non-trivial responses
