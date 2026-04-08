# Transaction Consistency And Workflow

## Transaction Boundaries

Define transaction scope at use case level.
Keep transactional decisions close to policy intent.

## Consistency Modes

- Strong consistency for critical invariants.
- Eventual consistency for cross-boundary workflows.
- Compensating actions for distributed failure paths.

## Workflow Orchestration

- Use use cases for local orchestration.
- Use process managers/sagas for long-running workflows.
- Keep orchestration state explicit and observable.

## Reliability Patterns

- Idempotent commands and handlers.
- Outbox/inbox for message reliability.
- Retry with bounded policy and jitter.
- Dead-letter handling with operational visibility.
