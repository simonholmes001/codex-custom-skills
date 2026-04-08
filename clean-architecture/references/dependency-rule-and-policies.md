# Dependency Rule And Policies

## Dependency Rule

Source code dependencies point inward.
Outer layers know inner layers.
Inner layers do not know outer layers.

## Policy Layers

- Entities and value objects: enterprise-wide business rules.
- Use cases/interactors: application-specific policies and orchestration.
- Interface adapters: translation between external and internal representations.
- Frameworks and drivers: web, DB, messaging, UI, and infrastructure details.

## Practical Enforcement

- Restrict imports across layer boundaries.
- Keep infrastructure packages out of domain layer.
- Define ports in inner layers, implementations in outer layers.
- Add architecture tests to enforce dependency direction.

## Decision Heuristics

- If a change in framework forces domain edits, boundary is leaking.
- If use case logic lives in controllers, policy is misplaced.
- If adapters contain business decisions, use case layer is too thin.
