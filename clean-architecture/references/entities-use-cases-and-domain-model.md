# Entities Use Cases And Domain Model

## Entities And Value Objects

- Model core business concepts and invariants.
- Keep state transitions explicit and valid by construction.
- Prefer value objects to reduce primitive obsession.

## Use Cases (Interactors)

- Represent one application behavior per interactor.
- Accept input models and return output models.
- Coordinate entities and ports without framework concerns.
- Keep orchestration deterministic and test-friendly.

## Modeling Rules

- Express business language directly in types and methods.
- Keep side effects outside entity logic when possible.
- Use explicit policies for authorization and validation.

## Complexity Controls

- Split long workflows into smaller use cases.
- Avoid god use cases handling unrelated paths.
- Extract domain services only when behavior spans entities.
