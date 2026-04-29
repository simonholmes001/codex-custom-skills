---
name: application-architecture-patterns
description: Select and apply application architecture patterns with explicit tradeoff analysis. Use when a user asks to choose architecture style, compare monolith vs microservices, evaluate layered/hexagonal/CQRS/event-driven options, define boundaries, or plan architecture migration.
---

# Application Architecture Patterns

## Overview

Use this skill to choose architecture patterns intentionally rather than by default. Tie pattern choices to context, constraints, and expected evolution of the system.

## Workflow

1. Establish drivers and constraints.
2. Build candidate pattern set.
3. Compare tradeoffs.
4. Recommend target architecture.
5. Plan migration increments.

## 1) Establish Drivers and Constraints

Capture:
- domain complexity and rate of change
- team topology and ownership boundaries
- operational maturity and platform capabilities
- latency, consistency, and scaling requirements

## 2) Build Candidate Pattern Set

Start with likely options from `references/pattern-selection-matrix.md`.

## 3) Compare Tradeoffs

Evaluate each candidate for:
- coupling and deployability
- testability and change isolation
- data ownership and integration complexity
- observability and operational burden

## 4) Recommend Target Architecture

Produce one primary recommendation and one fallback, each with:
- rationale
- risks
- disqualifiers

## 5) Plan Migration Increments

Define staged transition:
1. establish boundaries and interfaces
2. extract or isolate one vertical slice
3. validate with telemetry and tests
4. repeat in controlled increments

## Output Contract

Return:
1. `Context Summary`
2. `Pattern Comparison`
3. `Recommended Architecture`
4. `Migration Plan`
5. `Risks / Assumptions`

## References

- Read `references/pattern-selection-matrix.md`.
- Read `references/examples.md` for usage examples.
- Cross-use with `$clean-architecture` and `$non-functional-requirements`.
