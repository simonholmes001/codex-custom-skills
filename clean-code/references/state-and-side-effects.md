# State And Side Effects

## State Management Principles

- Prefer immutable data for shared flows.
- Keep mutable state local and short-lived.
- Avoid shared mutable globals.

## Side Effect Isolation

- Isolate I/O behind clear interfaces.
- Centralize boundary interactions (DB, network, filesystem).
- Keep pure domain logic free of external dependencies.

## Concurrency Safety

- Make ownership and synchronization explicit.
- Avoid implicit race-prone shared data.
- Use deterministic patterns for retries and backoff.

## Time And Randomness

- Inject clocks and random sources for testability.
- Avoid calling wall clock directly in domain logic.
- Record deterministic seeds when randomness is required.
