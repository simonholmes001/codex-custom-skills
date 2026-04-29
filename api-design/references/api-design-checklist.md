# API Design Checklist

## Contract Semantics

- Clear resource or command naming.
- Consistent HTTP/gRPC/event semantics.
- Explicit field requirements and defaults.

## Compatibility

- Non-breaking change policy defined.
- Versioning strategy documented.
- Deprecation windows and communication path defined.

## Safety

- Idempotency for retriable operations.
- Concurrency control (ETag/version) where needed.
- Authorization and data-scoping rules explicit.

## Operability

- Structured error model with machine-readable codes.
- Pagination/filtering/sorting conventions.
- Correlation and request tracing fields.
