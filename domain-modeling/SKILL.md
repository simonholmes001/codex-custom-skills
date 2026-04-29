---
name: domain-modeling
description: Model business domains into clear bounded contexts, aggregates, entities, value objects, and invariants. Use when a user asks to define domain boundaries, map business rules, identify aggregates, model commands/events, or fix anemic domain models.
---

# Domain Modeling

## Overview

Use this skill to transform ambiguous business concepts into explicit domain models and enforceable invariants. Keep language aligned with the business and minimize leakage of persistence concerns.

## Workflow

1. Establish domain language.
2. Identify bounded contexts.
3. Define aggregates and invariants.
4. Map interactions and integration.
5. Validate with scenarios.

## 1) Establish Domain Language

Capture terms, synonyms, and forbidden ambiguous names. Normalize on one ubiquitous language per context.

## 2) Identify Bounded Contexts

Define context boundaries by:
- ownership and lifecycle differences
- invariant boundaries
- conflicting terminology

## 3) Define Aggregates and Invariants

For each aggregate:
- root entity
- value objects
- invariant rules
- allowed state transitions

Use `references/domain-modeling-canvas.md`.

## 4) Map Interactions and Integration

Define:
- commands and domain events
- consistency boundary (strong/eventual)
- anti-corruption mappings between contexts

## 5) Validate With Scenarios

Test model fitness against real business scenarios and edge cases.

## Output Contract

Return:
1. `Context Map`
2. `Aggregate Definitions`
3. `Invariant Catalog`
4. `Command/Event Model`
5. `Gaps / Risks / Assumptions`

## References

- Read `references/domain-modeling-canvas.md`.
- Read `references/examples.md` for usage examples.
- Cross-use with `$clean-architecture` and `$application-architecture-patterns`.
