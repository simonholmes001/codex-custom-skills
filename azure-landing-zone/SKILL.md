---
name: azure-landing-zone
description: Design, assess, and implement Azure landing zones using Microsoft Cloud Adoption Framework and Azure Landing Zones guidance. Use when Codex needs to define management group hierarchy, subscription vending, platform vs workload boundaries, design-area decisions, governance/security baselines, network topology, and deployment/adoption sequencing for enterprise Azure estates.
---

# Azure Landing Zone

## Overview

Use this skill to produce production-ready Azure landing zone designs and rollout plans aligned to CAF and Azure Landing Zones reference implementations.

## Workflow

1. Confirm enterprise scope: tenant boundaries, regions, compliance constraints, and operating model.
2. Define target hierarchy: management groups, platform subscriptions, landing-zone subscriptions, sandbox/decommission flows.
3. Work through design areas: identity, management, security, network topology, governance, platform automation.
4. Select deployment path: portal/accelerator/IaC and phased onboarding strategy.
5. Define policy and guardrails first, then workload onboarding.
6. Validate with control checks, risk review, and rollback/fallback paths.

## Load References Selectively

- For canonical links and authoritative sources, read `references/official-docs.md`.
- For CAF principles and architecture intent, read `references/design-principles.md`.
- For design-area decision mapping, read `references/design-areas-checklist.md`.
- For deployment options and sequencing, read `references/deployment-approaches.md`.
- For practical ALZ implementation posture, read `references/alz-implementation-guidance.md`.

## Design Rules

Apply these rules consistently:
1. Separate platform foundation from workload subscriptions.
2. Define management group hierarchy before policy assignment sprawl.
3. Enforce policy-as-code and deny-by-default where appropriate.
4. Prefer hub-spoke or Virtual WAN based on scale and transit complexity.
5. Standardize identity and privileged access controls early.
6. Instrument centralized logging and security telemetry from day one.
7. Onboard workloads only after landing zone guardrails are validated.
8. Track exceptions with owner, rationale, expiry, and compensating controls.

## Output Contract

For each landing-zone answer:
1. State target-state architecture in concise bullets.
2. Map major design decisions to CAF/ALZ principles.
3. List required platform controls and guardrails.
4. Provide phased implementation plan and workload onboarding path.
5. Include validation checks, risks, and rollback strategy.

## Delivery Templates

When useful, structure output as:
- `Landing Zone Decision Record` (context, options, selected path)
- `Design Area Matrix` (area -> decision -> control)
- `Implementation Backlog` (foundation, migration, hardening)
