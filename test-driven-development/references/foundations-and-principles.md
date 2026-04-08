# Foundations And Principles

## What TDD Is

Test-Driven Development is a design and delivery discipline:

- Specify behavior with a failing test.
- Implement the minimum code to pass.
- Improve structure safely while tests stay green.

Use tests as the first consumer of your API.
Write production code only in response to a failing test.

## Core Objectives

- Keep defect rates low by validating behavior continuously.
- Improve design by forcing clear boundaries and dependencies.
- Maintain fast, reliable changeability of the codebase.
- Capture requirements as executable documentation.

## Canonical Loop

1. Red: Write a failing test that expresses one behavior.
2. Green: Make that test pass with the smallest correct change.
3. Refactor: Remove duplication and improve clarity while preserving behavior.

## Quality Bar

- Keep feedback fast: run a narrow test slice first.
- Keep tests deterministic: no dependence on wall clock, random seeds, or shared mutable state.
- Keep tests intention-revealing: name scenario, condition, and expectation.
- Keep failures diagnostic: failure messages should explain what broke.

## TDD Mindset

- Think in examples before implementation details.
- Prefer many small cycles over large speculative implementations.
- Let failing tests shape API ergonomics and object boundaries.
- Treat refactoring as mandatory, not optional cleanup.

## When TDD Is Most Valuable

- Domain logic with significant branching and invariants.
- Bug fixes requiring reproducible regressions.
- Public APIs where behavior must remain stable.
- Legacy modules where safe change requires characterization tests.
- Team environments where tests become shared understanding.

## Tradeoffs To Manage

- Initial speed may feel slower during learning or setup.
- Overly detailed tests can freeze implementation freedom.
- Poorly chosen test levels can inflate runtime and brittleness.
- Strict TDD without pragmatic exceptions can block exploratory spikes.

## Practical Exceptions

Allow temporary deviation only with explicit reason:

- Prototype or spike to discover unknowns.
- Irreducible external behavior needing instrumentation first.
- Critical emergency patch where reproducer arrives after mitigation.

After deviation, return to TDD by writing missing regression and characterization tests.
