# Codex Skills Repository

This repository contains your custom Codex skills, extracted from local Codex configuration so they can be versioned and published.

It is the single source of truth for reusable operating guidance you want Codex to follow across projects.

## What This Repo Contains

- Curated, reusable skills for architecture, engineering quality, testing, Azure operations, networking, GitHub operations, and review workflows.
- One folder per skill.
- A `SKILL.md` file in each skill folder (required).
- Optional supporting material in `references/` for deeper guidance.

## Skill Sets (Short Descriptions)

- `azure-architecture`
  Designs secure, scalable Azure platform and workload architectures, including landing zones, governance, identity boundaries, and rollout sequencing.
- `azure-mcp`
  Defines a safe read-first workflow for inspecting and operating Azure resources through MCP, with explicit change control and validation.
- `azure-networking`
  Covers Azure network topology design and troubleshooting across VNets, peering, routing, DNS, private access, and segmentation controls.
- `clean-architecture`
  Guides boundary-first system design so business rules stay independent from frameworks, infrastructure, and delivery mechanisms.
- `clean-code`
  Enforces maintainable coding and refactoring practices focused on readability, cohesion, error handling, and safe incremental improvements.
- `gh-project-ops`
  Provides strict, reliable GitHub Project auth and command preflight rules so project board operations always use the correct `gh` workflow.
- `github-mcp`
  Standardizes GitHub issue/PR/repo operations via MCP with explicit safety boundaries and predictable execution steps.
- `pull-request-review`
  Applies a security-first, risk-based PR review method that prioritizes actionable findings by severity and operational impact.
- `test-driven-development`
  Uses Red-Green-Refactor micro-cycles to drive implementation from tests and keep behavior changes safe and verifiable.

## Repository Structure

```text
skills/
├── README.md
├── azure-architecture/
│   ├── SKILL.md
│   └── references/
├── azure-mcp/
│   ├── SKILL.md
│   └── references/
├── azure-networking/
│   ├── SKILL.md
│   └── references/
├── clean-architecture/
│   ├── SKILL.md
│   └── references/
├── clean-code/
│   ├── SKILL.md
│   └── references/
├── gh-project-ops/
│   └── SKILL.md
├── github-mcp/
│   ├── SKILL.md
│   └── references/
├── pull-request-review/
│   ├── SKILL.md
│   └── references/
└── test-driven-development/
    ├── SKILL.md
    └── references/
```

## How Codex Uses These Skills

Codex can apply a skill when:
- You explicitly reference it (for example: `$clean-code`, `$test-driven-development`).
- The task clearly matches the skill scope.

Each `SKILL.md` defines:
- When to use the skill.
- The workflow Codex should follow.
- Optional reference files to load selectively.

## Local Development Workflow

1. Edit a skill directly in this repository.
2. Validate the skill text for clarity and command correctness.
3. Sync the updated skill(s) into `~/.codex/skills` when needed for local use.

Example sync command:

```bash
cp -R /Users/simonholmes/Projects/Applications/skills/<skill-name> /Users/simonholmes/.codex/skills/
```

## Authoring Standards

For each skill:
- Keep scope explicit and narrow.
- Use concrete workflows (ordered steps).
- Prefer safe, deterministic commands.
- Include references only when they add operational value.
- Keep guidance short, opinionated, and executable.

## Why This Repo Exists

- Prevent skill drift across machines/sessions.
- Keep hard-won operational knowledge persistent.
- Make skill improvements reviewable with normal Git workflows.
- Prepare a clean path to publish/share skills on GitHub.
