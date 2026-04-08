# API And Interface Design

## Interface Principles

- Design for clear usage paths and safe defaults.
- Minimize required knowledge to use correctly.
- Keep interfaces small and composable.

## Stability And Evolution

- Preserve backward compatibility intentionally.
- Version breaking changes explicitly.
- Deprecate with migration guidance.

## Data Contracts

- Validate boundaries strictly.
- Use explicit schemas where possible.
- Avoid overexposed internal fields.

## Ergonomics

- Prefer predictable naming and parameter ordering.
- Make common cases simple and uncommon cases possible.
- Surface failure and timeout behavior clearly.
