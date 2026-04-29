# Pattern Selection Matrix

## Layered Architecture

- Best for: simple to moderate business complexity.
- Strengths: straightforward structure, fast onboarding.
- Risks: anemic domain model, layer leakage.

## Hexagonal (Ports/Adapters)

- Best for: rich domain logic and integration-heavy systems.
- Strengths: testability, framework isolation.
- Risks: upfront abstraction cost.

## Modular Monolith

- Best for: cohesive domain with multiple bounded contexts not yet requiring independent deploy.
- Strengths: simpler operations, strong internal boundaries.
- Risks: erosion into a big ball of mud without governance.

## Event-Driven

- Best for: asynchronous workflows and decoupled integration.
- Strengths: temporal decoupling, scalable integration.
- Risks: eventual consistency complexity and debugging difficulty.

## CQRS

- Best for: divergent read/write models and high read scale.
- Strengths: optimized query and command paths.
- Risks: model duplication, synchronization overhead.

## Microservices

- Best for: high domain and org scale with mature platform operations.
- Strengths: independent deployability and ownership.
- Risks: operational and data-consistency complexity.
