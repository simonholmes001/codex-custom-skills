# Mocks Fakes And Test Doubles

## Decision Rules

- Use real collaborators by default when cost is low.
- Use fakes for heavy infrastructure (DB, queue, file storage) when realistic behavior is needed.
- Use mocks when interaction is the behavior under test.
- Use stubs when only fixed return values are needed.

## Avoid Brittle Interaction Tests

- Assert essential interactions only.
- Avoid verifying call order unless business-critical.
- Avoid asserting full argument objects when one field matters.
- Refactor code when mock setup dominates test readability.

## Favor Fakes For Domain Confidence

Fakes are often better than mocks because they preserve behavior semantics.

Examples:

- In-memory repository fake honoring unique constraints.
- Fake mailer collecting sent messages for assertion.
- Fake clock supporting deterministic time progression.

## Anti-Patterns

- Mocking the system under test itself.
- Mocking value objects or pure functions.
- Asserting every internal call path.
- Using networked dependencies in unit tests.

## External Boundary Strategy

At external boundaries, combine:

- Unit tests with doubles for speed.
- Integration tests against sandbox/local emulators where possible.
- Contract tests for schema and behavior guarantees.
