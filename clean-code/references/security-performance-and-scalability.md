# Security Performance And Scalability

## Security Baselines

- Validate and sanitize all external input.
- Apply least privilege for credentials and access.
- Avoid secret leakage in code, logs, and errors.
- Use safe defaults for authentication and authorization.

## Performance Baselines

- Measure before optimizing.
- Optimize hot paths and high-volume operations.
- Control allocation churn and avoid unnecessary copies.
- Cache deliberately with invalidation strategy.

## Scalability Baselines

- Keep state partitionable when growth is expected.
- Design idempotent operations for retries.
- Bound queue growth and concurrency.
- Plan for graceful degradation under load.

## Clean Code Connection

Security and performance code should remain readable:

- Prefer explicit policy objects over scattered conditionals.
- Encapsulate optimization complexity behind clear interfaces.
- Document non-obvious constraints and tradeoffs.
