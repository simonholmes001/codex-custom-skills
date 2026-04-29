---
name: api-design
description: Design robust application APIs and contracts with compatibility and operability in mind. Use when a user asks for REST/gRPC/event API design, endpoint/resource modeling, versioning strategy, idempotency, pagination/filtering, error schema, or backward-compatible contract changes.
---

# API Design

## Overview

Use this skill to design API contracts that are explicit, evolvable, and operationally safe. Prefer clear semantics and compatibility guarantees over convenience shortcuts.

## Workflow

1. Define API purpose and consumers.
2. Design contract shape.
3. Define safety and compatibility rules.
4. Specify operational concerns.
5. Produce implementation-ready contract artifacts.

## 1) Define API Purpose and Consumers

Capture:
- consumer types (internal service, frontend, partner)
- critical workflows and SLAs
- data sensitivity and authorization model

## 2) Design Contract Shape

Decide:
- style (REST, gRPC, event contract)
- resource/operation taxonomy
- request/response schemas

Use `references/api-design-checklist.md`.

## 3) Define Safety and Compatibility Rules

Specify:
- idempotency guarantees
- versioning and deprecation policy
- backward/forward compatibility rules

## 4) Specify Operational Concerns

Include:
- error model and retry guidance
- pagination, filtering, sorting behavior
- observability fields (request IDs, correlation IDs)

## 5) Produce Implementation-Ready Artifacts

Return concrete endpoint/method specs and examples.

## Output Contract

Return:
1. `API Summary`
2. `Contract Specification`
3. `Compatibility and Versioning Policy`
4. `Operational Behavior`
5. `Risks / Open Questions`

## References

- Read `references/api-design-checklist.md`.
- Read `references/examples.md` for usage examples.
- Cross-use with `$non-functional-requirements` and `$architecture-decision-records`.
