---
name: azure-architecture
description: Design Azure cloud architectures and enterprise landing zones using Microsoft best practices. Use when Codex needs to plan or review Azure platform foundations, subscription hierarchy, management groups, identity and access, governance, networking, security controls, workload placement, resilience, cost optimization, or environment rollout patterns.
metadata:
  category: azure
  subdomain: platform-architecture
  owner: custom
---

# Azure Architecture

## Overview

Design production-ready Azure platforms and workload architectures with clear tradeoffs, guardrails, and rollout sequencing. Prioritize secure-by-default landing zones, operational simplicity, and scalable governance.

## Workflow

1. Gather business, compliance, and workload constraints.
2. Define landing zone baseline (identity, governance, network, security, operations).
3. Map workloads to architecture decisions (compute, data, integration, connectivity).
4. Validate against reliability, security, performance, cost, and operations criteria.
5. Produce phased implementation plan with validation and rollback points.

## Load References Selectively

- For foundation and platform boundaries, read `references/landing-zone-blueprint.md`.
- For quality checks and architecture tradeoffs, read `references/architecture-review-checklist.md`.
- For governance, identity, and security guardrails, read `references/governance-security-baseline.md`.
- For service and topology choices, read `references/decision-patterns.md`.
- For Microsoft authoritative guidance and current best practices, read `references/official-docs.md`.

## Inputs Checklist

Collect before recommending architecture:
- Business criticality and recovery targets (RTO, RPO)
- Regulatory constraints and data residency requirements
- Environments (dev/test/stage/prod) and isolation model
- Connectivity requirements (Internet, on-prem, partner, multi-region)
- Identity model (Entra ID tenant boundaries, B2B/B2C needs)
- Cost envelope and scaling expectations
- Team operating model (central platform vs app team ownership)

## Design Rules

Apply these rules consistently:
1. Separate platform foundation from workload subscriptions.
2. Use management groups and policy-as-code for guardrails first.
3. Use hub-and-spoke or Virtual WAN for shared connectivity at scale.
4. Prefer private service connectivity for sensitive data paths.
5. Standardize observability and security telemetry from day one.
6. Define failure domains and cross-zone/region strategy explicitly.
7. Design for least privilege with RBAC and managed identities.
8. Enforce tagging, naming, and budget controls at onboarding time.

## Landing Zone Scope

Always include:
- Management group hierarchy and subscription vending pattern
- Identity and access boundary model
- Network topology and egress strategy
- Policy initiatives and exemption process
- Logging/monitoring architecture and retention controls
- Backup/DR posture and key workload dependencies
- Secure software supply chain and deployment guardrails

## Output Contract

For every architecture answer:
1. Provide target-state architecture in concise bullets.
2. Explain major tradeoffs and why the recommendation fits.
3. List required guardrails and platform controls.
4. Provide phased rollout plan (foundation, migration, hardening).
5. Include validation checks, risks, and rollback strategy.

## Delivery Templates

When useful, structure output as:
- `Architecture Decision Record` bullets for major choices
- `Landing Zone Backlog` with prioritized work items
- `Control Matrix` mapping risks to Azure controls

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
