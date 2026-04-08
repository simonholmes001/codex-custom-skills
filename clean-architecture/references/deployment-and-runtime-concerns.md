# Deployment And Runtime Concerns

## Runtime Composition

- Keep composition root explicit for each deployable unit.
- Make infrastructure bindings environment-specific but policy-invariant.

## Observability By Boundary

- Add logs, traces, and metrics at adapter boundaries and use case execution.
- Include correlation identifiers across async workflows.
- Track failure domains per adapter.

## Resilience

- Bound retries and timeouts by use case criticality.
- Apply circuit breakers and bulkheads at external boundaries.
- Expose degraded mode behavior explicitly.

## Configuration Discipline

- Keep config in outer layer.
- Validate configuration at startup.
- Avoid configuration branching in domain policies.
