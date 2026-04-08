# Frameworks Drivers And Infrastructure

## Placement

Treat frameworks as delivery mechanisms, not architectural center.
Keep framework dependencies in outermost modules.

## Infrastructure Responsibilities

- Implement gateway ports.
- Configure dependency injection/composition root.
- Handle integration concerns: retries, timeouts, caching, tracing.

## Containment Strategy

- Wrap third-party SDKs with local adapters.
- Avoid propagating framework annotations across inner layers.
- Keep migration cost bounded by stable internal contracts.

## Composition Root

Compose object graph at startup in one place.
Bind interfaces to concrete adapters.
Keep composition logic separate from use case logic.
