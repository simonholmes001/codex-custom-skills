---
name: assurance-engineering
description: Apply assurance engineering to Azure and AI solutions by identifying control objectives, validating evidence, assessing residual risk, and producing prioritized remediation plans. Use when Codex needs to perform security and operational assurance reviews, architecture/control gap assessments, AI safety guardrail reviews, readiness checks before go-live, or continuous assurance plans tied to Azure best practices and Well-Architected principles.
---

# Assurance Engineering

## Overview

Use a repeatable assurance workflow to turn architecture details into verified control posture and actionable remediation. Focus on evidence-backed conclusions, explicit risk statements, and operationally realistic next steps.

## Workflow

1. Define scope boundaries.
2. Identify control objectives.
3. Evaluate control design and effectiveness.
4. Score risk and detect assurance gaps.
5. Produce a prioritized remediation plan with evidence requirements.

## Step 1: Define Scope Boundaries

Capture the workload boundary before assessing controls:
- System context, trust boundaries, and data classifications
- Deployment model and environments (dev/test/prod)
- Critical business processes and failure impact
- Regulatory, contractual, or policy obligations
- Stakeholders who own control operation and evidence

## Step 2: Identify Control Objectives

Select applicable objectives using the mapped references:
- Azure security baseline objectives (identity, secrets, network, data protection, operations)
- Operational excellence objectives (standardization, observability, automation, safe deployment)
- AI safety objectives (prompt-injection resilience, safety filtering, runtime guardrails)

Use `references/assurance-control-checklist.md` for a quick control set.

## Step 3: Evaluate Design and Effectiveness

For each control, assess both:
- Design adequacy: whether the control is suitable for the risk
- Operating effectiveness: whether implementation evidence supports actual operation

Prefer evidence over assertions. Ask for concrete artifacts when absent:
- IaC policies, RBAC assignments, and configuration snapshots
- Pipeline definitions and quality gates
- Alerting/monitoring dashboards and runbooks
- Incident records, drill logs, and postmortems
- AI safety settings and evaluation outputs

## Step 4: Score Risk and Detect Gaps

For each gap, record:
- Risk statement (threat, asset, impact)
- Likelihood and impact rationale
- Current compensating controls
- Residual risk after current controls
- Assurance confidence level (`high`, `medium`, `low`) based on evidence quality

## Step 5: Produce the Assurance Output

Use this output contract:
1. Scope summary and assumptions.
2. Control-by-control assessment table.
3. Top risks ordered by severity.
4. Remediation backlog (owner, priority, sequencing, effort).
5. Evidence plan for unresolved findings.

## Severity Model

Apply this scale:
- `Critical`: active exploit path or likely major business/regulatory impact
- `High`: substantial control failure with plausible exploitation path
- `Medium`: notable weakness with constrained exploitability or impact
- `Low`: hygiene or optimization gap with limited immediate risk

## Load References Selectively

- Read `references/source-index.md` for source links and update metadata.
- Read `references/assurance-control-checklist.md` for practical controls and evidence prompts.

## Rules

1. Separate documented facts from inference; label assumptions explicitly.
2. Do not mark a control effective without at least one evidence artifact.
3. Prefer small, testable remediation increments over broad rewrites.
4. Tie every recommendation to risk reduction and operability impact.
5. Keep findings falsifiable: include what evidence would disprove the finding.

## Default Prompt Pattern

Use this prompt shape when useful:
`Assess this Azure/AI solution using assurance engineering. Identify control objectives, evaluate evidence quality, rate residual risk, and return a prioritized remediation plan aligned to Azure security and operational excellence guidance.`
