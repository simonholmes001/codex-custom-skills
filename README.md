# Skills Repository

This repository stores custom Codex skills used for local and plugin-assisted workflows.

## What This Repo Contains

- Top-level folders: one folder per custom skill (for example `api-design`, `azure-architecture`, `microsoft-agent-framework`).
- `.system/`: system-level skills and support assets used by Codex runtime behaviors.
- Each skill typically includes:
  - `SKILL.md` (instructions and workflow)
  - `agents/` (agent configuration)
  - `references/` (supporting guidance)
  - `scripts/` (utility scripts when needed)
  - `assets/` (icons/images when needed)

## Source of Truth

The canonical local source for mirrored skill content is:

- `~/.codex/skills`

This repo is intended to track that content in git so changes can be reviewed, versioned, and shared.

## Sync Model

Typical update flow:

1. Update skill content under `~/.codex/skills`.
2. Mirror changes into this repository.
3. Commit and push to `main`.

## Notes

- Generated runtime artifacts (for example `__pycache__`) should not be tracked.
- This repository is content-focused; it does not itself execute skills unless consumed by a Codex environment.
