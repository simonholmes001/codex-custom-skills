---
name: non-functional-requirements
description: Translate non-functional requirements into concrete architecture and implementation constraints. Use when a user asks to define SLIs/SLOs, reliability/performance/security targets, observability requirements, resilience expectations, or validation plans for quality attributes.
metadata:
  category: architecture-design
  subdomain: application-design
  owner: custom
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

## Quick vs Deep Mode Policy

Use this decision policy to balance depth, cost, and response speed:

### Quick Mode (default)

Use when the request is narrow, exploratory, or low-risk.

1. Read `SKILL.md` and `references/cross-skill-standards.md`.
2. Read only the minimum task-relevant references for the scoped request.
3. In the response, state:
- references read
- references intentionally not read
- confidence level (`Verified`, `Derived`, `Assumption`)

### Deep Mode (mandatory full source pass)

Switch to Deep Mode when any of the following is true:

1. The request drives production, go-live, or high-blast-radius decisions.
2. The request has security, compliance, legal, or financial risk implications.
3. The request asks for comprehensive, authoritative, or sign-off-quality guidance.
4. The request includes major architecture or migration commitments.
5. Quick Mode leaves material uncertainty, conflicting evidence, or low confidence.

In Deep Mode, execute the skill's fullest available source pass workflow for its domain before final recommendations.

### Escalation Rule

Start in Quick Mode unless high-stakes triggers are already explicit. Escalate to Deep Mode immediately when uncertainty remains material.

## Cross-Skill Standards

Read and apply `references/cross-skill-standards.md` for:

- Evidence quality rubric (`Verified`, `Derived`, `Assumption`)
- Context-budget/loading policy
- Anti-pattern and handoff rules
- Source freshness policy
- Minimum output additions for non-trivial responses
