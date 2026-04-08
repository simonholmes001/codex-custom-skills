# Modular Monolith And Microservices

## Decision Principle

Choose boundaries based on business capability and team ownership, not trend.

## Modular Monolith First

- Start with internal modules and strict boundaries.
- Enforce dependency rule between modules.
- Keep cross-module communication explicit.

## Service Extraction Criteria

Extract to microservices when there is clear need:

- Independent scaling profile.
- Independent release cadence.
- Strong ownership and bounded context stability.
- Measurable coupling reduction.

## Extraction Strategy

- Stabilize module contracts first.
- Introduce anti-corruption adapters.
- Move one capability at a time.
- Preserve observability and rollback paths.

## Warning Signs

- Premature service split causing distributed complexity.
- Shared database across services without clear ownership.
- Cross-service chatty dependencies replacing in-process calls.
