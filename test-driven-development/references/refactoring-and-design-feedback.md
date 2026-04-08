# Refactoring And Design Feedback

## Use TDD As Design Pressure

Let failing tests expose design friction:

- Hard setup indicates hidden dependencies.
- Repetitive assertions indicate weak abstractions.
- Difficult naming indicates unclear domain model.

Refactor toward explicit boundaries and intention-revealing names.

## Refactor Triggers

Refactor when you observe:

- Duplication across tests or production code.
- Long methods with multiple responsibilities.
- Conditional complexity that obscures business rules.
- Coupling that blocks isolated testing.

## Safe Refactor Protocol

1. Start from green.
2. Make one structural change.
3. Re-run affected tests.
4. Commit if still green.
5. Repeat.

Avoid combining feature changes with deep refactor in one step.

## Patterns That Pair Well With TDD

- Extract Function for dense logic blocks.
- Introduce Value Object for primitive obsession.
- Replace Conditional with Polymorphism for branching rules.
- Introduce Ports/Adapters to isolate infrastructure.
- Separate Command from Query to simplify assertions.

## Design Smells Exposed By Tests

- Tests needing massive fixture setup.
- Tests asserting many unrelated outcomes.
- Tests breaking from harmless internal refactors.
- Needing many mocks to instantiate one class.

Respond by reducing coupling and increasing cohesion.
