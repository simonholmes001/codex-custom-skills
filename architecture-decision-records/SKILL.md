---
name: architecture-decision-records
description: Create and maintain architecture decision records (ADRs) with clear context, alternatives, rationale, and consequences. Use when a user asks to document major technical decisions, compare options formally, capture decision rationale, or update/supersede prior architecture decisions.
---

# Architecture Decision Records

## Overview

Use this skill to produce high-quality ADRs that are concise, auditable, and actionable. Keep decision history explicit so teams can understand why choices were made.

## Workflow

1. Frame the decision.
2. Gather alternatives.
3. Evaluate tradeoffs.
4. Record decision and consequences.
5. Define follow-up actions.

## 1) Frame the Decision

Capture:
- decision statement
- scope and affected systems
- forcing constraints

## 2) Gather Alternatives

Include realistic options, including a `do nothing` baseline.

## 3) Evaluate Tradeoffs

Assess options against:
- business impact
- engineering complexity
- operational risk
- reversibility

Use `references/adr-template.md`.

## 4) Record Decision and Consequences

Document:
- selected option and rationale
- positive and negative consequences
- migration/rollback expectations

## 5) Define Follow-Up Actions

Add validation tasks, owners, and re-evaluation triggers.

## Output Contract

Return:
1. `ADR Draft`
2. `Option Comparison`
3. `Consequences`
4. `Implementation and Validation Tasks`
5. `Review Triggers`

## References

- Read `references/adr-template.md`.
- Read `references/examples.md` for usage examples.
- Cross-use with `$application-architecture-patterns`, `$api-design`, and `$non-functional-requirements`.
