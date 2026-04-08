# codex-custom-skills

A public collection of practical Codex skills for software engineering, architecture, cloud operations, and delivery workflows.

These skills are designed to be directly usable in real projects and easy to adapt to your own standards.

## What Is In This Repository

Each folder is one skill. A skill includes:
- `SKILL.md` (required): scope, workflow, and execution guidance
- optional `references/`: deeper playbooks and checklists
- optional `agents/`: model-specific defaults

Current skill sets:
- `azure-architecture`: Azure landing zones, governance, identity boundaries, and platform/workload architecture decisions.
- `azure-mcp`: Safe Azure operations through MCP with read-first diagnostics and controlled changes.
- `azure-networking`: Azure networking design and troubleshooting (VNet, NSG, routing, DNS, private connectivity).
- `clean-architecture`: Boundary-first architecture with strict dependency direction and policy isolation.
- `clean-code`: Maintainable coding and refactoring standards for readability, reliability, and long-term changeability.
- `gh-project-ops`: Reliable GitHub Project operations with strict `gh` auth/preflight command rules.
- `github-mcp`: GitHub issue/PR/repo workflows via MCP with explicit safety boundaries.
- `pull-request-review`: Security-first, risk-based PR review framework with severity-driven findings.
- `test-driven-development`: Practical Red-Green-Refactor loops for behavior-first implementation.

## Clone vs Fork

Use **clone** if you only want to use these skills as-is.

Use **fork** if you plan to modify, version, and maintain your own variant (recommended for teams).

## Quick Start

### Option A: Clone and use as-is

```bash
git clone https://github.com/simonholmes001/codex-custom-skills.git
cd codex-custom-skills
```

### Option B: Fork and customize

1. Fork this repository on GitHub.
2. Clone your fork:

```bash
git clone https://github.com/<your-username>/codex-custom-skills.git
cd codex-custom-skills
```

## Install Skills Locally (Codex)

Copy the skill folders you want into your local Codex skills directory:

```bash
cp -R ./<skill-name> ~/.codex/skills/
```

Install all skills from this repo:

```bash
cp -R ./* ~/.codex/skills/
```

Then start a new Codex session so the skills are loaded.

## Using Skills In Prompts

Reference skills explicitly in your prompt (examples):
- `$clean-code`
- `$test-driven-development`
- `$pull-request-review`
- `$azure-architecture`

You can combine skills when needed, for example:
- `$clean-architecture` + `$test-driven-development`
- `$azure-mcp` + `$azure-networking`

## Repository Structure

```text
codex-custom-skills/
├── README.md
├── azure-architecture/
├── azure-mcp/
├── azure-networking/
├── clean-architecture/
├── clean-code/
├── gh-project-ops/
├── github-mcp/
├── pull-request-review/
└── test-driven-development/
```

## Contributing

Contributions are welcome.

Suggested process:
1. Open an issue describing the skill improvement.
2. Submit a PR with focused changes.
3. Keep guidance concrete, executable, and safety-aware.

## Versioning Your Own Team Standard

If you fork this repo, treat your fork as an internal standard:
- pin a branch or tag for team-wide consistency
- review skill updates like production docs/code
- sync local `~/.codex/skills` from your forked source of truth

## License

Add a license file before broad redistribution (for example, MIT).
