# Functions And Methods

## Function Design

- Make each function do one coherent thing.
- Keep function scope tight and intention-revealing.
- Favor early returns to reduce nesting.
- Keep data transformation explicit.

## Arguments

- Prefer small argument lists.
- Group related arguments into value objects.
- Avoid boolean flag arguments that switch behavior.
- Keep argument order stable and unsurprising.

## Side Effects

- Make side effects explicit and localized.
- Separate computation from I/O where practical.
- Avoid hidden mutation of inputs.

## Return Values

- Return domain-meaningful values.
- Use explicit result types for success/failure when language supports it.
- Avoid magic values and sentinel ambiguity.

## Complexity Management

- Split large branching logic into named predicates or strategy objects.
- Extract duplicated logic only when intent becomes clearer.
- Remove dead paths and redundant checks.
