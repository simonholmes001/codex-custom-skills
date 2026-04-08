# Framework Recipes

## Language-Agnostic Workflow

- Run a single test file or case first.
- Run impacted module/package tests second.
- Run full suite before finalizing change.

## JavaScript / TypeScript

- Common test frameworks: Jest, Vitest, Mocha.
- Unit test command pattern: `npm test -- <pattern>`.
- Watch mode for rapid loops: `npm test -- --watch`.
- Prefer fake timers for time-based behavior.

## Python

- Common test frameworks: pytest, unittest.
- Unit test command pattern: `pytest path/to/test_file.py -k <name>`.
- Use fixtures for setup reuse and explicit dependencies.
- Use `freezegun` or clock injection for time control.

## Java / Kotlin

- Common test frameworks: JUnit, TestNG.
- Mocking tools: Mockito, MockK.
- Use Testcontainers for realistic integration dependencies when needed.
- Keep domain logic testable without Spring context where possible.

## Go

- Use standard `testing` package by default.
- Run focused tests: `go test ./... -run <TestName>`.
- Use table-driven tests for behavior matrices.
- Use interfaces and small seams for dependency isolation.

## C#

- Common frameworks: xUnit, NUnit, MSTest.
- Common mocking libraries: Moq, NSubstitute.
- Prefer explicit Arrange-Act-Assert structure.
- Keep integration tests isolated with dedicated test fixtures.

## Ruby

- Common frameworks: RSpec, Minitest.
- Use expressive behavior-based naming.
- Keep shared examples focused and avoid over-abstraction.

## Rust

- Use built-in `cargo test` plus focused module tests.
- Prefer pure function design for fast unit coverage.
- Use integration tests in `tests/` for crate boundary behavior.

## Framework Selection Guidance

- Prefer the repository's existing test stack.
- Add new tooling only with clear gap and team agreement.
- Optimize for maintainability and CI consistency over novelty.
