# Design Principles Notes

Use CAF landing zone principles to shape all architecture recommendations.

## Principle Themes

- Subscription democratization: application teams get subscriptions with guardrails pre-applied.
- Single control and management plane: unified governance and operations model.
- Application-centric and archetype-driven design: standard subscription/landing-zone patterns.
- Platform automation and DevOps: repeatable provisioning and policy assignment.

## Practical Consequences

1. Treat landing zone as a product with versioned controls and platform backlog.
2. Minimize bespoke one-off subscription designs.
3. Keep policy and identity controls consistent across environments.
4. Balance central governance with delegated workload ownership.

## Anti-Patterns to Avoid

- Building workload infrastructure before guardrails exist.
- Flat subscription sprawl with no MG policy inheritance strategy.
- Manual ad-hoc role assignments without operating model ownership.
- Inconsistent telemetry/security baseline across subscriptions.
