# Design Principles Checklist

## SOLID

- Single Responsibility: one reason to change.
- Open/Closed: add behavior via extension, not repeated edits.
- Liskov Substitution: subtype behavior honors base contract.
- Interface Segregation: narrow consumer-focused interfaces.
- Dependency Inversion: high-level policy depends on abstractions.

## Simplicity

- KISS: prefer the simplest design meeting requirements.
- YAGNI: avoid speculative abstraction.
- DRY: remove duplicated behavior, not just duplicated text.

## Structure

- High cohesion within modules.
- Low coupling between modules.
- Composition over inheritance when reuse is behavioral.
- Explicit boundaries for side effects (I/O, network, clock, randomness).

## Refactoring Priority Signals

- Shotgun surgery across many files for one behavior change.
- God objects/modules with mixed concerns.
- Circular dependencies or unstable import graphs.
- Hidden temporal coupling and mutable global state.
