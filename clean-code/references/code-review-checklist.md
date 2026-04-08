# Code Review Checklist

## Correctness

- Does the change satisfy requirements and edge cases?
- Are invariants preserved?
- Are error paths explicit and tested?

## Readability

- Are names precise and domain-aligned?
- Is control flow easy to follow?
- Is complexity proportionate to the problem?

## Design

- Are responsibilities well-separated?
- Are dependencies appropriate and directional?
- Is public surface area minimal and clear?

## Reliability

- Are failures observable and actionable?
- Are retries/timeouts/circuit-breaking appropriate?
- Are race conditions or state hazards introduced?

## Tests

- Do tests cover intended behavior and key edge cases?
- Are tests deterministic and maintainable?
- Is the right test level used for each concern?

## Operational Impact

- Any migration, rollout, or rollback concerns?
- Any security, performance, or cost implications?
- Any backward compatibility risks?
