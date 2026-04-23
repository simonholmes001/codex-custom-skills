# ALZ Implementation Guidance

## Operating Model Expectations

- Define clear ownership between platform and application teams.
- Publish landing-zone archetypes (for example prod, non-prod, sandbox).
- Keep platform changes governed by release management.

## Minimum Platform Baseline

- Management groups and subscription archetypes.
- Policy baseline (regions, tags, diagnostic settings, encryption, public access constraints).
- Identity baseline (least privilege, PIM, access reviews).
- Central logging/monitoring and security telemetry pipeline.

## Workload Onboarding Pattern

1. Classify workload criticality and data sensitivity.
2. Select approved subscription archetype.
3. Apply platform bootstrap and policy packs.
4. Run readiness checks before go-live.

## Drift and Lifecycle Management

- Detect and remediate control drift continuously.
- Time-bound all policy exemptions.
- Re-validate landing-zone assumptions during major architecture changes.
