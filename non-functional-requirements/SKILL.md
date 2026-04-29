---
name: non-functional-requirements
description: Translate non-functional requirements into concrete architecture and implementation constraints. Use when a user asks to define SLIs/SLOs, reliability/performance/security targets, observability requirements, resilience expectations, or validation plans for quality attributes.
---

# Non Functional Requirements

## Overview

Use this skill to convert vague quality attributes into measurable, testable constraints that guide architecture and engineering choices.

## Workflow

1. Elicit quality attributes.
2. Define measurable targets.
3. Map targets to design constraints.
4. Define validation and observability.
5. Track residual risk.

## 1) Elicit Quality Attributes

Capture priority and context for:
- reliability and availability
- latency and throughput
- scalability and cost efficiency
- security and compliance
- observability and operability

## 2) Define Measurable Targets

Express as SLO/SLA-style targets with units and windows.

## 3) Map Targets to Design Constraints

Convert each target into concrete design and implementation constraints using `references/nfr-catalog.md`.

## 4) Define Validation and Observability

Specify:
- tests (load, chaos, failover, security)
- runtime indicators (SLIs, alerts, dashboards)
- rollback and mitigation triggers

## 5) Track Residual Risk

List unmet targets, temporary exceptions, and decision owners.

## Output Contract

Return:
1. `NFR Matrix`
2. `Design Constraints`
3. `Validation Plan`
4. `Telemetry and Alerting Requirements`
5. `Residual Risk Register`

## References

- Read `references/nfr-catalog.md`.
- Read `references/examples.md` for usage examples.
- Cross-use with `$azure-architecture`, `$application-architecture-patterns`, and `$twelve-factor-app`.
