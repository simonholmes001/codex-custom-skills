# Testing And Testability

## Testability By Design

- Inject dependencies to isolate units.
- Keep deterministic logic separate from side effects.
- Design boundaries that are easy to fake or stub.

## Test Suite Quality

- Favor fast unit tests for logic coverage.
- Add integration tests for boundary confidence.
- Keep end-to-end tests focused on critical journeys.

## Test Readability

- Name tests by behavior and expectation.
- Use Arrange-Act-Assert or equivalent clear structure.
- Keep fixtures explicit and minimal.

## Maintainability

- Prevent brittle tests tied to internals.
- Remove duplicate setup with concise helpers.
- Fix flaky tests immediately.
