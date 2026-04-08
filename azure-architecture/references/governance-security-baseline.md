# Governance and Security Baseline

## Identity Baseline

- Require MFA for all privileged roles.
- Use PIM for just-in-time elevation where possible.
- Limit permanent global and subscription owner assignments.
- Review access recertification periodically.

## Policy Baseline

Enforce at management group scope by default:
- Allowed locations and approved resource types
- Mandatory tags and tag inheritance strategy
- Diagnostic settings to central logging
- Encryption and secure transport requirements
- Public network access restrictions where applicable

## Subscription Baseline

- Use dedicated subscriptions for platform services.
- Separate production from non-production.
- Enable budgets and cost alerts at subscription scope.
- Standardize RBAC group mapping per subscription role model.

## Network Security Baseline

- Segment workloads by subnet and security boundary.
- Apply deny-by-default network policy patterns.
- Centralize egress controls for regulated workloads.
- Validate DNS and routing path ownership explicitly.

## Data Security Baseline

- Classify data and map controls by classification.
- Use private endpoints for sensitive PaaS data flows.
- Enforce backup, retention, and restore testing cadence.
- Define key management and rotation ownership.

## Operations and Detection Baseline

- Centralize logs with retention policy by control objective.
- Define critical alerts, thresholds, and owner rotation.
- Integrate cloud alerts with incident management workflows.
- Run periodic security posture reviews and remediation sprints.

## Exception Handling

- Record policy exceptions with reason, owner, and end date.
- Require periodic review and auto-expiry where possible.
- Reject exceptions without compensating controls for critical risk.
