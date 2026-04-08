# Example Directory Shapes

## Modular Monolith Example

```text
src/
  domain/
    entities/
    value-objects/
    services/
  application/
    use-cases/
    ports/
  adapters/
    inbound/
      http/
      cli/
    outbound/
      persistence/
      messaging/
      external-clients/
  infrastructure/
    config/
    composition-root/
    framework/
```

## Service-Oriented Example

```text
services/
  billing/
    domain/
    application/
    adapters/
    infrastructure/
  catalog/
    domain/
    application/
    adapters/
    infrastructure/
shared/
  contracts/
  observability/
```

Use these as directional templates, not rigid standards.
