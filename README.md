# Codex Custom Skills

This repository version-controls a custom skills catalog for Codex.

## Purpose

- Track custom skill definitions in git.
- Mirror local skill-source updates from `~/.codex/skills`.
- Keep skill guidance shareable, reviewable, and reproducible.

## Repository Layout

- `CATALOG.md`: high-level skill catalog/index.
- `<skill-name>/SKILL.md`: primary instructions for each skill.
- `<skill-name>/references/`: supporting standards, templates, and source-backed guidance.
- `.system/`: system-level skills and supporting assets/scripts.

## Sync Workflow

1. Update skills in `~/.codex/skills`.
2. Mirror content into this repository.
3. Commit and push to `main`.

## Scope Notes

- Runtime artifacts (for example `__pycache__`) are local noise and should not be tracked.
- This repository stores skill content; execution happens when consumed by a Codex runtime.
