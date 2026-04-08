# Testing Strategy By Layer

## Domain And Use Case Tests

- Unit test entities, value objects, and use cases without framework boot.
- Test business invariants and edge cases thoroughly.
- Keep tests deterministic and fast.

## Adapter Tests

- Test controllers and presenters for translation correctness.
- Test repository/client adapters against expected contracts.
- Verify mapping and error translation behavior.

## Integration Tests

- Validate composed workflows across real boundaries.
- Focus on persistence behavior, transaction semantics, and serialization.
- Keep fixtures explicit and isolated.

## Architecture Tests

- Enforce import/dependency direction.
- Detect forbidden references to outer frameworks in core modules.
- Fail CI when boundaries drift.

## End-To-End Tests

- Keep small and critical-journey focused.
- Use to validate system wiring, not all business permutations.
