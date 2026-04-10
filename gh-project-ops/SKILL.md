---
name: gh-project-ops
description: Use this skill for GitHub Project board manipulation. Includes mandatory authentication and scope preflight steps before running gh project commands.
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
