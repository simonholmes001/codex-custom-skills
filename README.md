# Codex Custom Skills

[![Last Commit](https://img.shields.io/github/last-commit/simonholmes001/codex-custom-skills/main)](https://github.com/simonholmes001/codex-custom-skills/commits/main)
[![Open Issues](https://img.shields.io/github/issues/simonholmes001/codex-custom-skills)](https://github.com/simonholmes001/codex-custom-skills/issues)
[![Open PRs](https://img.shields.io/github/issues-pr/simonholmes001/codex-custom-skills)](https://github.com/simonholmes001/codex-custom-skills/pulls)
[![Codex Skills](https://img.shields.io/badge/Codex-Skills%20Catalog-0A66C2)](https://github.com/simonholmes001/codex-custom-skills)

This repository version-controls a custom skills catalog for Codex and provides a reusable source of skill definitions.

## Quick Start

1. Clone this repository:
   ```bash
   git clone https://github.com/simonholmes001/codex-custom-skills.git
   cd codex-custom-skills
   ```
2. Copy skills into your local Codex skills directory:
   ```bash
   rsync -a --delete --exclude '.git/' --exclude '__pycache__/' ./ ~/.codex/skills/
   ```
3. Start Codex and use skills from this catalog.

## How To Use Skills

- Browse available skills in `CATALOG.md`.
- Open each skill's `SKILL.md` to understand trigger conditions, workflow, and constraints.
- Invoke skills in Codex by:
  - naming the skill directly (for example `$api-design`), or
  - using a request that clearly matches a skill's described use case.
- Treat `.system/` content as system-level support skills and assets rather than regular domain skills.

## Repository Layout

- `CATALOG.md`: high-level skill catalog/index.
- `<skill-name>/SKILL.md`: primary instructions for each skill.
- `<skill-name>/references/`: supporting standards, templates, and source-backed guidance.
- `<skill-name>/scripts/`: helper scripts used by some skills.
- `<skill-name>/assets/`: images or static assets used by some skills.
- `.system/`: system-level skills and support assets/scripts.

## Contributing and Authoring

When adding or updating a skill:

1. Keep the core instruction set in `SKILL.md`.
2. Add source-backed material to `references/` when claims need grounding.
3. Keep scripts idempotent and scoped to the skill where possible.
4. Update `CATALOG.md` when adding new skills or changing purpose.
5. Verify changes in a local Codex run before opening a PR.

## Sync Workflow

Current operating model:

1. Update skills in local source directory `~/.codex/skills`.
2. Mirror content into this repository.
3. Commit and push to `main`.

Mirror exclusions:

- `.git/`
- `__pycache__/`

## Compatibility and Scope

- This repository stores skill content; execution happens when consumed by a Codex runtime.
- Skill behavior can vary with Codex runtime updates; validate important changes in your environment.

## License

No root license file is currently defined for this repository. Add a `LICENSE` file before broad redistribution.
