# Code Review Checklist

## Dependency Direction

- Do imports flow inward toward policy?
- Are forbidden layer dependencies prevented?

## Boundary Integrity

- Are ports defined on the policy side?
- Are adapters translation-only and thin?
- Do contracts avoid framework-specific leakage?

## Use Case Quality

- Does each use case represent one coherent behavior?
- Are business rules in use cases/entities rather than controllers?
- Are orchestration and side effects explicit?

## Infrastructure Containment

- Are framework/SDK specifics confined to outer layers?
- Is composition root clear and centralized?

## Test Coverage

- Are core policies tested without framework boot?
- Are adapter and integration tests covering boundary behavior?
- Are architecture tests enforcing constraints?
