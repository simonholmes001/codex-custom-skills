---
name: architecture-decision-records
description: Create and maintain architecture decision records (ADRs) with clear context, alternatives, rationale, and consequences. Use when a user asks to document major technical decisions, compare options formally, capture decision rationale, or update/supersede prior architecture decisions.
metadata:
  category: architecture-design
  subdomain: decision-records
  owner: custom
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
