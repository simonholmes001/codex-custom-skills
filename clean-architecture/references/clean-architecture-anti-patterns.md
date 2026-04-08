# Clean Architecture Anti-Patterns

## Framework-Centered Core

Symptom: domain and use cases depend directly on framework types.
Correction: introduce ports and isolate framework code in adapters.

## Anemic Use Case Layer

Symptom: controllers or handlers contain business rules.
Correction: move orchestration and policy decisions into interactors.

## Leaky Boundaries

Symptom: DTOs, ORM entities, or HTTP objects cross into core policies.
Correction: map explicitly at boundaries.

## God Adapter

Symptom: one adapter handles validation, policy, persistence, and formatting.
Correction: split concerns; adapters translate, use cases decide.

## Circular Module Dependencies

Symptom: policy and infrastructure import each other.
Correction: enforce one-way dependency flow with architecture tests.

## Big-Bang Migration

Symptom: full rewrite attempted before stabilization.
Correction: migrate by capability with seams, tests, and cutover controls.

## Missing Architecture Tests

Symptom: boundaries erode silently over time.
Correction: add CI checks for dependency and layering constraints.
