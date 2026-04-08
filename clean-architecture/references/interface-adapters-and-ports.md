# Interface Adapters And Ports

## Ports

Define boundaries as interfaces in the policy side.
Common categories:

- Input ports: use case entry points.
- Output ports: presenters or notification boundaries.
- Gateway ports: persistence, messaging, or external services.

## Adapters

Implement ports on the outer side.
Translate between external protocols and internal models.

Typical adapters:

- Controllers/handlers (HTTP, CLI, event handlers).
- Presenters/view models.
- Repository and client adapters.

## Adapter Rules

- Keep adapters thin and translation-focused.
- Keep business rules out of controllers and repositories.
- Do not leak ORM, transport, or framework types into use cases.
