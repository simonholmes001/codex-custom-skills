---
name: app-design-principles
description: Apply core software design principles to application code and architecture decisions. Use when a user asks for design review, refactoring guidance, modularity/cohesion/coupling improvements, SOLID/DRY/KISS/YAGNI application, or maintainability-driven restructuring of application code.
metadata:
  category: architecture-design
  subdomain: application-design
  owner: custom
---

# App Design Principles

## Overview

Use this skill to run a principle-driven design review and convert findings into concrete refactoring or design actions. Keep recommendations tied to code evidence and delivery constraints.

## Workflow

1. Define context and constraints.
2. Inspect design surfaces.
3. Evaluate principle adherence.
4. Prioritize tradeoffs.
5. Produce targeted changes.

## 1) Define Context and Constraints

Capture:
- business goal and critical use cases
- delivery constraints (timeline, team size, backward compatibility)
- non-functional drivers (performance, reliability, security)

## 2) Inspect Design Surfaces

Focus on:
- module boundaries and imports
- class/function responsibilities
- dependency direction and inversion points
- state ownership and mutation patterns
- public contracts and extension seams

## 3) Evaluate Principle Adherence

Use `references/design-principles-checklist.md`.

For each finding, include:
- principle involved
- evidence (file/path and behavior)
- risk if unchanged
- smallest viable remediation

## 4) Prioritize Tradeoffs

Prioritize by:
- correctness and defect risk
- change amplification and maintainability cost
- delivery impact and migration complexity

Prefer incremental refactors with behavior-preserving tests.

## 5) Produce Targeted Changes

When implementation is requested:
- edit the minimal set of files
- avoid broad rewrites without explicit approval
- add tests around changed seams

## Output Contract

Return:
1. `Design Summary`
2. `Findings by Principle`
3. `Prioritized Refactoring Plan`
4. `Concrete Code Changes` (if requested)
5. `Residual Risks / Assumptions`

## References

- Read `references/design-principles-checklist.md` for review criteria.
- Read `references/examples.md` for usage examples.
- Cross-use with `$clean-code`, `$clean-architecture`, and `$test-driven-development` when needed.

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
