# Language Specific Notes

## JavaScript And TypeScript

- Use strict linting and type checks.
- Avoid implicit `any` and ambiguous union narrowing.
- Prefer pure helpers for transformation-heavy logic.

## Python

- Prefer explicitness and readable control flow.
- Use type hints for public interfaces.
- Keep data models and service boundaries clear.

## Java And Kotlin

- Keep domain logic independent from framework annotations where possible.
- Prefer immutable value types.
- Limit inheritance depth; favor composition.

## Go

- Keep packages small and purpose-driven.
- Return explicit errors and wrap with context.
- Avoid hidden globals; inject dependencies.

## C#

- Favor clear async boundaries and cancellation handling.
- Use records/value objects for domain clarity where appropriate.
- Keep DI registration aligned with explicit lifetimes.

## Rust

- Use type system and ownership to encode invariants.
- Keep lifetimes and traits readable, not over-generalized.
- Separate unsafe blocks behind safe APIs.

## Ruby

- Prefer intention-revealing method names and small objects.
- Keep metaprogramming constrained and documented.
- Avoid excessive callback chains that hide control flow.
