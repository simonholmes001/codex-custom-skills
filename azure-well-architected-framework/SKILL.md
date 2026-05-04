---
name: azure-well-architected-framework
description: Apply the Azure Well-Architected Framework to assess and improve workload architecture across pillars, architect role practices, reliability engineering, and performance monitoring with evidence-based tradeoff decisions.
metadata:
  category: azure
  subdomain: well-architected
  owner: custom
---

# Azure Well-Architected Framework

## Overview

Use this skill to perform evidence-backed Azure Well-Architected assessments and architecture improvements.

Primary outcomes:

- Clear mapping from business goals to architecture requirements.
- Pillar-aware tradeoff decisions with explicit consequences.
- Reliability engineering grounded in flow analysis and failure modes.
- Continuous improvement backlog with measurable validation gates.

This skill is source-grounded. For non-trivial recommendations, run a full source pass before synthesis.

## Mandatory Source Pass

Before providing architecture guidance, design reviews, modernization plans, or production hardening advice:

1. Read `references/source-index.md` for canonical scope.
2. Read `references/source-pass-protocol.md` and execute it end-to-end.
3. Complete `references/source-coverage-matrix.md` for relevant sections.
4. Then load detailed references (`review-template`, `reliability-playbook`) for synthesis.

If a request is narrowly scoped (for example only reliability metrics), run a scoped source pass for the relevant matrix sections and state what was intentionally out of scope.

## Workflow

1. Capture business and technical requirements.
2. Perform source pass and record coverage.
3. Define architecture intent with ADR and design-spec discipline.
4. Assess across all Well-Architected pillars.
5. Perform reliability flow mapping and failure mode analysis.
6. Define metrics, tradeoffs, and target maturity.
7. Produce prioritized improvement roadmap with validation and rollback criteria.

## Load References

- Canonical source inventory: `references/source-index.md`
- Full-pass protocol and evidence grading: `references/source-pass-protocol.md`
- Topic coverage checklist: `references/source-coverage-matrix.md`
- Structured review format: `references/review-template.md`
- Reliability analysis method: `references/reliability-playbook.md`

## Core Design Rules

1. Translate business requirements into measurable architecture outcomes.
2. Keep design auditable through ADRs and architecture specifications.
3. Evaluate all five pillars even when one pillar is the immediate driver.
4. Identify critical user/data/control-plane flows before resilience design.
5. Use explicit failure-mode analysis for high-impact flows.
6. Treat tradeoffs as first-class artifacts; record accepted risks and review cadence.
7. Use metrics/SLOs as release and operations gates.
8. Reassess architecture continuously as workload shape and risk posture change.
9. Separate source-verified facts from derived guidance and assumptions.

## Output Contract

For architecture/review responses, return:

1. `Context Summary`
2. `Source Coverage Summary` (read, skipped, and gaps)
3. `Pillar Assessment`
4. `Reliability Analysis`
5. `Architecture Decisions and Tradeoffs`
6. `Improvement Backlog and Validation Plan`
7. `Assumptions and Residual Risks`

## Evidence Expectations

Prefer concrete artifacts:

- Architecture design specification and diagrams
- ADRs with alternatives and consequences
- Flow inventories and FMA outputs
- Reliability SLIs/SLOs, incidents, and postmortems
- Monitoring/alert definitions with ownership and escalation
- Runbooks, drill records, and rollback procedures

## Cross-Skill Standards

Read and apply `references/cross-skill-standards.md` for:

- Evidence quality rubric (`Verified`, `Derived`, `Assumption`)
- Context-budget/loading policy
- Anti-pattern and handoff rules
- Source freshness policy
- Minimum output additions for non-trivial responses
