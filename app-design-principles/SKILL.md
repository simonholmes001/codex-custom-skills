---
name: app-design-principles
description: Apply core software design principles to application code and architecture decisions. Use when a user asks for design review, refactoring guidance, modularity/cohesion/coupling improvements, SOLID/DRY/KISS/YAGNI application, or maintainability-driven restructuring of application code.
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
