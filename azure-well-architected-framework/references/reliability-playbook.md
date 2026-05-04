# Reliability Playbook

Use this playbook when applying the Reliability pillar.

## 1) Identify Critical Flows

- Enumerate user journeys and system workflows that drive business value.
- Mark dependencies (identity, network, data, external APIs, control planes).
- Define impact if each flow degrades or fails.

## 2) Perform Failure Mode Analysis (FMA)

- For each critical component, list plausible failure modes.
- Record blast radius, detection signal, and recovery action.
- Assign ownership and expected recovery time.

## 3) Choose Redundancy and Simplification Strategy

- Select zonal/region redundancy by business criticality.
- Remove unnecessary complexity that increases failure probability.
- Validate failover assumptions with test evidence.

## 4) Define Reliability Metrics

- Track availability, latency, error rate, and durability where relevant.
- Define SLO targets and alert thresholds per critical flow.
- Tie metrics to runbooks and escalation paths.

## 5) Manage Tradeoffs

- Document reliability vs cost/performance tradeoffs explicitly.
- Capture accepted risks and revisit cadence.
