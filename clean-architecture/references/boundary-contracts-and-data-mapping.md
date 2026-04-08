# Boundary Contracts And Data Mapping

## Contract Design

- Define explicit input/output DTOs at boundaries.
- Keep boundary schemas versioned and documented.
- Validate external inputs before entering use case layer.

## Mapping Rules

- Map once at boundaries; avoid ad hoc conversions everywhere.
- Keep internal models independent from transport and persistence format.
- Preserve semantic meaning during translation.

## Compatibility Strategy

- Use additive changes when possible.
- Support transition windows for breaking changes.
- Keep backward compatibility policy explicit per boundary.

## Anti-Leak Checks

- No ORM entities crossing into domain use case APIs.
- No HTTP-specific types inside core policies.
- No vendor SDK types in domain models.
