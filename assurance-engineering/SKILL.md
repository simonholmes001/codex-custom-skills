---
name: assurance-engineering
description: Apply assurance engineering to Azure and AI solutions by identifying control objectives, validating evidence, assessing residual risk, and producing prioritized remediation plans. Use when Codex needs to perform security and operational assurance reviews, architecture/control gap assessments, AI safety guardrail reviews, readiness checks before go-live, or continuous assurance plans tied to Azure best practices and Well-Architected principles.
metadata:
  category: general
  subdomain: security-assurance
  owner: custom
---

# Assurance Engineering

## Overview

Use a repeatable assurance workflow to convert architecture and operational details into verified control posture, explicit residual risk statements, and prioritized remediation actions.

Primary outcomes:

- Evidence-backed control assessments (design + operating effectiveness).
- Clear risk register with confidence scoring.
- Sequenced remediation backlog tied to measurable risk reduction.
- Explicit evidence plan for unresolved findings.

This skill is source-grounded. For non-trivial assessments, complete a full source pass before conclusions.

## Mandatory Source Pass

Before providing assurance conclusions, go-live readiness calls, or remediation prioritization:

1. Read `references/source-index.md` for canonical source scope and freshness metadata.
2. Read `references/source-pass-protocol.md` and execute it end-to-end.
3. Complete `references/source-coverage-matrix.md` for relevant sections.
4. Use `references/assurance-control-checklist.md` for structured assessment execution.

If a request is narrow (for example AI safety guardrails only), run a scoped source pass and state out-of-scope sections.

## Workflow

1. Define scope boundaries.
2. Perform source pass and record coverage.
3. Identify applicable control objectives.
4. Evaluate design adequacy and operating effectiveness.
5. Score residual risk and assurance confidence.
6. Produce prioritized remediation and evidence plan.

## Load References

- Canonical sources and freshness metadata: `references/source-index.md`
- Full-pass protocol and evidence grading: `references/source-pass-protocol.md`
- Coverage checklist by control area: `references/source-coverage-matrix.md`
- Practical controls and evidence prompts: `references/assurance-control-checklist.md`

## Step 1: Define Scope Boundaries

Capture:
- System context, trust boundaries, and data classifications
- Deployment model and environments (dev/test/prod)
- Critical business processes and failure impact
- Regulatory/contractual obligations
- Stakeholders owning control operation and evidence

## Step 2: Identify Control Objectives

Select objectives across:
- Azure security baseline domains (identity, secrets, network, data, operations)
- Operational excellence domains (standards, observability, automation, safe deployment)
- AI safety domains (prompt-injection resilience, safety filtering, runtime guardrails)

## Step 3: Evaluate Design and Effectiveness

For each control:

- `Design adequacy`: is the control suitable for the threat and context?
- `Operating effectiveness`: is there credible evidence the control works in practice?

Do not rate controls effective without at least one concrete evidence artifact.

## Step 4: Score Risk and Detect Gaps

For each gap, record:

- Risk statement (threat, asset, impact)
- Likelihood and impact rationale
- Current compensating controls
- Residual risk after existing controls
- Assurance confidence (`high`, `medium`, `low`) based on evidence quality

## Step 5: Produce Assurance Output

Return:
1. `Scope Summary and Assumptions`
2. `Source Coverage Summary` (read, skipped, gaps)
3. `Control-by-Control Assessment`
4. `Top Risks` (ordered by severity)
5. `Remediation Backlog` (owner, priority, sequencing, effort)
6. `Evidence Plan` for unresolved findings
7. `Residual Risks and Confidence Notes`

## Severity Model

- `Critical`: active exploit path or likely major business/regulatory impact
- `High`: substantial control failure with plausible exploitation path
- `Medium`: notable weakness with constrained exploitability or impact
- `Low`: hygiene/optimization gap with limited immediate risk

## Rules

1. Separate documented facts from inference and assumptions.
2. Keep findings falsifiable: include evidence that could disprove a finding.
3. Prefer small, testable remediation increments over broad rewrites.
4. Tie each recommendation to risk reduction and operability impact.
5. Re-check source freshness when recommendations are high-stakes.

## Default Prompt Pattern

`Assess this Azure/AI solution using assurance engineering. Identify control objectives, evaluate evidence quality, rate residual risk, and return a prioritized remediation plan aligned to Azure security and operational excellence guidance.`

## Cross-Skill Standards

Read and apply `references/cross-skill-standards.md` for:

- Evidence quality rubric (`Verified`, `Derived`, `Assumption`)
- Context-budget/loading policy
- Anti-pattern and handoff rules
- Source freshness policy
- Minimum output additions for non-trivial responses
