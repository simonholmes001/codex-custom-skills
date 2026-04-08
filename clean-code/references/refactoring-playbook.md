# Refactoring Playbook

## Safe Refactoring Loop

1. Start from green tests.
2. Choose one structural improvement.
3. Make a small change.
4. Re-run targeted tests.
5. Repeat until intent is clear.

## Common Refactor Moves

- Rename for intent.
- Extract function.
- Inline unnecessary indirection.
- Introduce value object.
- Split module by responsibility.
- Replace conditionals with polymorphism where justified.

## Guardrails

- Do not mix unrelated behavioral changes.
- Keep commits reversible.
- Preserve public contracts unless explicitly changing them.
- Measure complexity reduction, not just line count reduction.

## Stop Conditions

Stop when:

- Readability is materially improved.
- Duplication and coupling are reduced.
- Additional refactor yields diminishing returns.
