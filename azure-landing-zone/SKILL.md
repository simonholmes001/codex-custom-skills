---
name: azure-landing-zone
description: Design, assess, and implement Azure landing zones using Microsoft Cloud Adoption Framework and Azure Landing Zones guidance. Use when Codex needs to define management group hierarchy, subscription vending, platform vs workload boundaries, design-area decisions, governance/security baselines, network topology, and deployment/adoption sequencing for enterprise Azure estates.
metadata:
  category: azure
  subdomain: landing-zone
  owner: custom
---

# Azure Landing Zone

## Overview

Use this skill to produce evidence-backed Azure landing zone architecture and rollout guidance aligned to CAF and Azure Landing Zones.

Primary outcomes:

- Clear platform/workload boundary design.
- Management group and subscription model with governance guardrails.
- Design-area decisions (identity, network, security, operations, automation) with tradeoffs.
- Phased onboarding plan with validation gates and rollback approach.

This skill is source-grounded. For non-trivial recommendations, perform a full source pass before synthesis.

## Mandatory Source Pass

Before providing target-state landing zone architecture, migration sequencing, policy strategy, or control posture recommendations:

1. Read `references/official-docs.md` for canonical scope.
2. Read `references/source-pass-protocol.md` and execute it end-to-end.
3. Complete `references/source-coverage-matrix.md` for relevant sections.
4. Then load `design-principles`, `design-areas-checklist`, `deployment-approaches`, and `alz-implementation-guidance` for synthesis.

If a request is scoped (for example network topology only), do a scoped source pass and explicitly state out-of-scope areas.

## Workflow

1. Confirm enterprise context (tenant boundaries, compliance, operating model, regions).
2. Perform source pass and record coverage.
3. Define management group hierarchy and subscription archetypes.
4. Work design areas end-to-end (identity, management, security, network, governance, automation).
5. Define policy and guardrails before workload onboarding.
6. Select deployment approach and rollout sequence.
7. Produce validation, risk, and rollback plan.

## Load References

- Canonical links and scope: `references/official-docs.md`
- Full-pass protocol and evidence grading: `references/source-pass-protocol.md`
- Topic coverage checklist: `references/source-coverage-matrix.md`
- CAF/ALZ principles: `references/design-principles.md`
- Design-area completeness: `references/design-areas-checklist.md`
- Deployment sequencing: `references/deployment-approaches.md`
- Practical implementation posture: `references/alz-implementation-guidance.md`

## Design Rules

1. Separate platform foundation subscriptions from workload subscriptions.
2. Define management group hierarchy before policy assignment sprawl.
3. Enforce policy-as-code with a clear exemption process.
4. Choose network topology based on scale/transit complexity and operations model.
5. Standardize identity and privileged-access controls early.
6. Establish centralized logging/security telemetry from day one.
7. Onboard workloads only after guardrail validation.
8. Track exceptions with owner, rationale, expiry, and compensating controls.
9. Separate source-verified facts from derived guidance and assumptions.

## Output Contract

For each landing-zone response, return:

1. `Context Summary`
2. `Source Coverage Summary` (read, skipped, gaps)
3. `Target-State Architecture`
4. `Design Area Decisions and Tradeoffs`
5. `Platform Controls and Guardrails`
6. `Phased Implementation and Onboarding Plan`
7. `Validation, Risks, and Rollback Strategy`

## Evidence Expectations

Prefer concrete artifacts:

- Management group and subscription hierarchy definitions
- Policy initiatives, assignments, and exemptions with ownership
- RBAC/PIM and privileged-access operating model evidence
- Network topology diagrams and routing/security controls
- Central monitoring/security configuration and retention settings
- Automation pipelines for subscription vending and guardrail rollout

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
