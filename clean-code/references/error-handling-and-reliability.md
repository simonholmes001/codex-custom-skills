# Error Handling And Reliability

## Error Semantics

- Distinguish domain errors from infrastructure failures.
- Attach actionable context without leaking secrets.
- Fail fast at boundaries when inputs are invalid.

## Handling Strategy

- Handle errors at the right level of abstraction.
- Avoid swallowing exceptions/errors silently.
- Preserve root cause information.
- Use retries only for transient failures with bounded policy.

## API Error Design

- Return stable, documented error shapes.
- Keep machine-readable codes and human-readable messages.
- Avoid ambiguous generic failures.

## Observability

- Emit logs with correlation identifiers.
- Include metrics for failure rate and latency.
- Make critical failures alertable.
