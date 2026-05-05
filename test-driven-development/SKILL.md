---
name: test-driven-development
description: Comprehensive guidance for test-driven development (TDD) across greenfield work, bug fixes, refactors, and legacy modernization. Use when Codex needs to translate requirements into failing tests, execute strict Red-Green-Refactor loops, choose and combine test levels (unit/integration/contract/e2e), design APIs through tests, control mocking strategy, stabilize flaky tests, or incrementally improve code quality without regressions.
metadata:
  category: engineering-practice
  subdomain: delivery-quality
  owner: custom
---

# Test-Driven Development

## Overview

Use this skill to deliver behavior through small, test-first increments.
Treat tests as executable specifications and design feedback, not just verification.

## Quick Start Protocol

1. State the next behavior in one sentence.
2. Choose the smallest test that would fail for that behavior.
3. Write the failing test first.
4. Implement the minimal production change to pass.
5. Run relevant tests to confirm green.
6. Refactor test and production code while staying green.
7. Repeat until acceptance criteria are covered.

## Load References By Need

- Read `references/foundations-and-principles.md` to align on TDD goals, values, and constraints.
- Read `references/red-green-refactor-workflow.md` to run disciplined micro-cycles and commit strategy.
- Read `references/test-design-techniques.md` to derive cases using equivalence classes, boundaries, and property checks.
- Read `references/test-levels-and-architecture.md` to choose unit vs integration vs contract vs e2e coverage.
- Read `references/mocks-fakes-and-test-doubles.md` to decide when to mock, fake, or use real collaborators.
- Read `references/refactoring-and-design-feedback.md` to use tests to improve structure and API shape.
- Read `references/legacy-code-and-characterization.md` to introduce TDD into hard-to-test systems.
- Read `references/flaky-tests-and-debugging.md` to diagnose nondeterminism and restore trust.
- Read `references/framework-recipes.md` for language-specific starter commands and conventions.
- Read `references/tdd-anti-patterns.md` to detect and correct common failure modes.

## Execution Rules

- Keep each Red-Green-Refactor loop short; prefer minutes, not hours.
- Create exactly one new failing assertion target per micro-cycle when possible.
- Pass tests with the simplest correct implementation before optimizing.
- Refactor only when green unless intentionally writing a temporary failing refactor test.
- Favor behavior-level assertions over implementation details.
- Avoid coupling tests to private internals unless the system boundary requires it.
- Keep test names descriptive of behavior and expected outcome.
- Use deterministic tests: control time, randomness, I/O, and concurrency.
- Preserve fast feedback by running focused tests first, then broader suites.

## Decision Defaults

- Default to unit-level TDD for domain logic.
- Add integration tests where component boundaries can break.
- Add contract tests for service-to-service interfaces.
- Keep e2e tests minimal and purpose-driven.
- Prefer fakes over mocks when interaction assertions become brittle.
- Introduce seams before rewriting legacy modules.

## Definition Of Done (TDD)

- Every accepted behavior is represented by tests that failed before implementation.
- Newly added tests are stable, deterministic, and readable.
- Production code passes linting, typing, and targeted quality gates.
- Refactor opportunities discovered during TDD are either addressed or logged.
- Commit history reflects small test-first steps where practical.

## Response Template During Task Execution

Use this structure when reporting TDD work progress:

1. `Behavior`: the exact behavior implemented in this cycle.
2. `Red`: failing test added and why it failed.
3. `Green`: minimal code change that made it pass.
4. `Refactor`: cleanup performed while preserving behavior.
5. `Risk`: unresolved edge cases, tradeoffs, or follow-up tests.

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
