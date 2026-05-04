# Codex Custom Skills

[![Last Commit](https://img.shields.io/github/last-commit/simonholmes001/codex-custom-skills/main)](https://github.com/simonholmes001/codex-custom-skills/commits/main)
[![Open Issues](https://img.shields.io/github/issues/simonholmes001/codex-custom-skills)](https://github.com/simonholmes001/codex-custom-skills/issues)
[![Open PRs](https://img.shields.io/github/issues-pr/simonholmes001/codex-custom-skills)](https://github.com/simonholmes001/codex-custom-skills/pulls)
[![Codex Skills](https://img.shields.io/badge/Codex-Skills%20Catalog-0A66C2)](https://github.com/simonholmes001/codex-custom-skills)

This repository provides a reusable catalog of custom Codex skills.

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

Contributions are welcome. If you want to add a new skill or improve an existing one:

1. Fork this repository (or create a branch if you already have write access).
2. Make your changes in the relevant skill folder.
3. Keep the main instructions in `SKILL.md`.
4. Add or update `references/` content for non-obvious or source-backed guidance.
5. Keep helper scripts scoped and repeatable.
6. Update `CATALOG.md` if you add, remove, or repurpose a skill.
7. Validate your change in a local Codex run.
8. Open a pull request that includes:
- what changed
- why it changed
- how you validated it
- any behavior changes or migration notes users should know

## Compatibility and Scope

- This repository stores skill content; execution happens when consumed by a Codex runtime.
- Skill behavior can vary with Codex runtime updates; validate important changes in your environment.

## License

No root license file is currently defined for this repository. Add a `LICENSE` file before broad redistribution.
