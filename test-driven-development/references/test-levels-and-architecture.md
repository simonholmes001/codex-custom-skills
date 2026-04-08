# Test Levels And Architecture

## Coverage Pyramid

Bias toward many fast unit tests, fewer integration tests, and minimal e2e tests.
Use contract tests to stabilize service boundaries.

## Unit Tests

Use for pure logic and small components.

- Fast execution.
- High branch coverage.
- Low infrastructure requirements.

Risk: over-mocking can hide integration defects.

## Integration Tests

Use for collaboration between real components.

- Persistence + domain logic.
- API controller + service + serialization.
- Queue producer + consumer contracts.

Keep data setup explicit and isolated.

## Contract Tests

Use for producer-consumer agreements between services.

- Validate schema, status codes, and required fields.
- Run in CI for both sides where possible.
- Version contracts intentionally.

## End-To-End Tests

Use sparingly for business-critical journeys.

- Login + key transaction flow.
- Purchase or onboarding path.

Keep suite small due to runtime and flakiness risk.

## Choosing Level For A New Behavior

1. Start at unit level if behavior is local.
2. Add integration tests if behavior crosses process or persistence boundaries.
3. Add contract tests if behavior affects external consumers.
4. Add e2e only if user-critical flow needs full-system confidence.

## Architecture Feedback Signals

If unit tests are hard to write, inspect design:

- Hidden global state.
- Tight coupling to I/O.
- Excessive constructor dependencies.
- Low-cohesion modules.

Introduce seams via ports/adapters, dependency injection, and pure functions.
