# Test Design Techniques

## Design Tests From Behavior

Define each test by three components:

- Context: initial state and relevant inputs.
- Action: single unit of behavior.
- Expectation: observable output, state, or interaction.

Prefer one clear behavioral claim per test.

## Equivalence Partitioning

Partition input space into classes expected to behave similarly.
Write at least one representative test per class.

Example classes:

- Valid well-formed input.
- Valid but edge-size input.
- Invalid format.
- Invalid business rule.

## Boundary Value Analysis

Focus on boundaries where behavior changes:

- Minimum/maximum limits.
- Off-by-one around thresholds.
- Empty vs non-empty collections.
- First/last item behavior.

## State Transition Testing

Model stateful workflows with transitions:

- Enumerate states.
- List valid transitions.
- Add tests for invalid transitions.

Useful for order lifecycle, auth flow, retries, and job orchestration.

## Property-Oriented Testing

When possible, define invariants instead of specific examples:

- Idempotency: applying operation twice equals once.
- Round-trip consistency: encode then decode preserves value.
- Commutativity or associativity where mathematically valid.

Use property tests for algorithmic or parser-heavy code.

## Error And Resilience Cases

Add explicit tests for:

- Timeouts and transient failures.
- Partial availability of dependencies.
- Retry and backoff behavior.
- Data corruption or malformed payloads.

## Test Naming Patterns

Use names that document behavior:

- `returns_error_when_token_is_expired`
- `applies_discount_at_quantity_threshold`
- `retries_three_times_on_502`

Avoid vague names like `test_happy_path`.

## Assertion Guidance

- Assert outcomes users or callers care about.
- Prefer one logical expectation per assertion block.
- Keep assertions specific enough to diagnose failure quickly.
- Avoid asserting private implementation details.
