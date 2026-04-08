# Clean Code Anti-Patterns

## Cleverness Over Clarity

Symptom: compact or advanced constructs obscure intent.
Correction: expand for readability and explicit behavior.

## God Objects And Utility Dumps

Symptom: unrelated responsibilities accumulate in one class/module.
Correction: split by domain capability and change axis.

## Primitive Obsession

Symptom: domain concepts represented as raw strings/numbers everywhere.
Correction: introduce value objects and typed boundaries.

## Boolean Flag Explosion

Symptom: functions take many booleans to steer behavior.
Correction: split functions or use explicit strategy types.

## Leaky Abstractions

Symptom: callers must understand internals to use API correctly.
Correction: redesign API contract and hide implementation details.

## Error Suppression

Symptom: failures are ignored or converted to generic responses.
Correction: propagate meaningful errors with context and codes.

## Comment-Driven Code

Symptom: comments explain complicated code that should be simplified.
Correction: refactor structure so intent is obvious without narration.

## Test Blind Spots

Symptom: changes merge with weak coverage on failure paths.
Correction: add targeted tests before and during refactor.
