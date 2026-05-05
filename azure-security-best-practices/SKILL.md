---
name: azure-security-best-practices
description: Apply Azure security best practices and patterns across identity, network, data, platform, operations, incident response, ransomware resilience, and AI security using Microsoft Learn fundamentals and Well-Architected guidance.
metadata:
  category: azure
  subdomain: security-assurance
  owner: custom
---

# Azure Security Best Practices

## Overview

Use this skill to produce evidence-backed Azure security architecture guidance, assurance findings, and remediation plans grounded in Microsoft Learn and related baseline guidance.

Primary outcomes:

- Explicit trust-boundary and attack-surface analysis.
- Domain-by-domain control assessment with evidence quality.
- Clear residual risk statements and prioritized remediation backlog.
- Validation plan with ownership and measurable completion criteria.

This skill is source-grounded. For non-trivial recommendations, perform a full source pass before synthesis.

## Mandatory Source Pass

Before providing security architecture recommendations, control assessments, go-live readiness opinions, or remediation plans:

1. Read `references/source-index.md` for canonical source scope.
2. Read `references/source-pass-protocol.md` and execute it end-to-end.
3. Complete `references/source-coverage-matrix.md` for relevant sections.
4. Then use `references/security-domains.md` and `references/assessment-template.md` for synthesis output.

If the request is narrow (for example only key management), run a scoped source pass for relevant matrix sections and explicitly declare what is out of scope.

## Workflow

1. Define scope, assets, trust boundaries, and exposure model.
2. Perform source pass and record coverage.
3. Classify data, identities, and privileged operations.
4. Assess controls by domain (identity, network, data/crypto, platform, monitoring/detection, IR/ransomware, AI security).
5. Score residual risk with evidence confidence and compensating controls.
6. Produce prioritized remediation plan with validation checks.

## Load References

- Canonical source set: `references/source-index.md`
- Full-pass protocol and evidence grading: `references/source-pass-protocol.md`
- Topic coverage checklist: `references/source-coverage-matrix.md`
- Domain control prompts: `references/security-domains.md`
- Output structure: `references/assessment-template.md`

## Core Design Rules

1. Apply Zero Trust: verify explicitly, least privilege, assume breach.
2. Minimize public exposure and prefer private connectivity for sensitive paths.
3. Use identity-first controls (MFA, conditional access, managed identity, PIM).
4. Treat secrets/keys/encryption lifecycle as first-class architecture concerns.
5. Ensure detection and response are designed, not bolted on.
6. Validate ransomware resilience with backup isolation and restore drills.
7. Include AI workload security controls where applicable.
8. Separate source-verified facts from derived guidance and assumptions.
9. Tie every recommendation to measurable risk reduction and operability impact.

## Severity Model

- `Critical`: active exploit path or likely major business/regulatory impact
- `High`: major control failure with plausible exploitation path
- `Medium`: meaningful weakness with constrained exploitability/impact
- `Low`: hygiene or optimization gap

## Output Contract

For each response, return:

1. `Scope Summary`
2. `Source Coverage Summary` (read, skipped, gaps)
3. `Control Assessment By Domain`
4. `Top Risks` (ordered by severity)
5. `Remediation Backlog` (priority, owner role, effort)
6. `Validation and Evidence Plan`
7. `Assumptions and Residual Risks`

## Evidence Expectations

Prefer concrete artifacts over assertions:

- IaC templates, policy assignments/exemptions, configuration snapshots
- RBAC/PIM/identity control evidence
- Network rules, WAF/firewall posture, private endpoint design
- Key management, encryption settings, and rotation evidence
- SIEM detections, alert routing, runbooks, and incident/drill records
- Backup immutability/isolation and restore test evidence
- AI safety controls and abuse/evaluation telemetry

## Cross-Skill Standards

Read and apply `references/cross-skill-standards.md` for:

- Evidence quality rubric (`Verified`, `Derived`, `Assumption`)
- Context-budget/loading policy
- Anti-pattern and handoff rules
- Source freshness policy
- Minimum output additions for non-trivial responses
