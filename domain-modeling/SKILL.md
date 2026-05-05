---
name: domain-modeling
description: Model business domains into clear bounded contexts, aggregates, entities, value objects, and invariants. Use when a user asks to define domain boundaries, map business rules, identify aggregates, model commands/events, or fix anemic domain models.
metadata:
  category: architecture-design
  subdomain: application-design
  owner: custom
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
