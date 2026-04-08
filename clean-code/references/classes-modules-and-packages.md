# Classes Modules And Packages

## Responsibility Boundaries

- Keep high cohesion within a module.
- Keep coupling between modules minimal and explicit.
- Organize by domain capability first.

## Dependency Direction

- Depend on abstractions where boundaries are stable.
- Keep domain logic independent from infrastructure details.
- Avoid circular dependencies.

## Class Design

- Prefer small classes with clear invariants.
- Keep constructors focused on required dependencies.
- Avoid god classes accumulating unrelated behaviors.

## Module Layout

- Co-locate code that changes together.
- Separate public API from internal implementation.
- Keep package boundaries visible and intentional.

## Encapsulation

- Expose minimal surface area.
- Protect invariants through methods and types.
- Avoid leaking internal representations.
