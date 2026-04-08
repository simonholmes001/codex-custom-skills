---
name: clean-architecture
description: Comprehensive clean architecture guidance for designing, reviewing, and refactoring software systems around stable boundaries and the dependency rule. Use when Codex needs to model entities and use cases, define ports and adapters, separate policy from implementation details, structure modules and services, design contracts and data mapping, test by architectural layer, or migrate legacy systems toward maintainable architecture without breaking behavior.
---

# Clean Architecture

## Overview

Use this skill to keep business policy independent from frameworks, databases, UI, and delivery mechanisms.
Design for replaceability at the edges and stability at the core.

## Quick Start Workflow

1. Clarify business capabilities and invariants.
2. Identify entities, value objects, and core use cases.
3. Define boundaries and dependency direction.
4. Model ports at boundary edges and adapters outside the core.
5. Keep framework and infrastructure details in outer layers.
6. Add tests by layer to protect architecture and behavior.
7. Refactor incrementally with compatibility and observability.

## Load References By Need

- Read `references/architecture-foundations.md` for principles and architecture fitness goals.
- Read `references/dependency-rule-and-policies.md` for dependency direction and policy isolation.
- Read `references/entities-use-cases-and-domain-model.md` for core domain modeling and interactor design.
- Read `references/interface-adapters-and-ports.md` for ports, adapters, controllers, presenters, and gateways.
- Read `references/frameworks-drivers-and-infrastructure.md` for infrastructure placement and framework boundaries.
- Read `references/boundary-contracts-and-data-mapping.md` for DTOs, schemas, and mapping strategy.
- Read `references/transaction-consistency-and-workflow.md` for orchestration, transactions, and eventual consistency.
- Read `references/testing-strategy-by-layer.md` for test strategy and architecture tests.
- Read `references/deployment-and-runtime-concerns.md` for runtime composition, observability, and reliability.
- Read `references/modular-monolith-and-microservices.md` for service-boundary tradeoffs and evolution strategy.
- Read `references/legacy-migration-playbook.md` for incremental migration from legacy systems.
- Read `references/code-review-checklist.md` for architecture-focused review checks.
- Read `references/language-and-framework-notes.md` for language-specific implementation advice.
- Read `references/example-directory-shapes.md` for practical project layout examples.
- Read `references/clean-architecture-anti-patterns.md` for quick anti-pattern detection.

## Default Execution Rules

- Enforce inward-only dependencies toward higher-level policy.
- Keep business rules framework-agnostic.
- Make boundaries explicit with contracts and mapping layers.
- Isolate side effects and infrastructure behind ports.
- Keep use cases small, deterministic, and intention-revealing.
- Treat architectural drift as a defect, not style preference.
- Refactor with compatibility plans, tests, and rollback options.

## Definition Of Done (Architecture)

- Dependency rule is visible in module dependencies and imports.
- Core policies can run without infrastructure frameworks.
- Boundary contracts are explicit and validated.
- Adapters translate between external formats and internal models.
- Architecture tests and behavior tests are green.
- Observability exists at key boundaries and workflows.
- Migration and tradeoff decisions are documented.

## Response Template During Task Execution

Use this structure when reporting architecture work:

1. `Context`: capability, constraints, and boundary assumptions.
2. `Design`: core policies, ports, adapters, and dependency direction.
3. `Implementation`: structural changes applied.
4. `Verification`: tests, architecture checks, and runtime validation.
5. `Risk`: residual coupling, migration concerns, and next steps.
