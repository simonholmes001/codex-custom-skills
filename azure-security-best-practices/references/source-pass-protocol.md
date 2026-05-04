# Source Pass Protocol (Mandatory)

Use this protocol whenever producing non-trivial guidance with this skill.

## Objective

Prevent shallow security recommendations by enforcing explicit source coverage, evidence quality grading, and falsifiable conclusions.

## Step 1: Scope and Threat Context

Capture:
- Workload boundary and critical assets
- Data sensitivity/classification
- Internet exposure and trust boundaries
- Regulatory/compliance drivers
- AI usage scope (if any)

## Step 2: Canonical Source Sweep

Read `source-index.md` and cover each relevant section from `source-coverage-matrix.md`.

Minimum for full security architecture guidance:
- Fundamentals/strategy (including Zero Trust)
- Identity and network/perimeter controls
- Secrets/keys/encryption controls
- Platform and infrastructure controls
- Monitoring/detection/IR/ransomware controls
- Data service security (SQL/Storage)
- AI security controls where applicable

## Step 3: Evidence Grading

For each major recommendation, mark:
- `Verified`: directly supported by canonical source content.
- `Derived`: inferred by combining verified sources.
- `Assumption`: not directly supported; requires validation.

Never present assumptions as verified facts.

## Step 4: Coverage Report

Return:
- Sections read
- Sections intentionally skipped (with reason)
- Source ambiguities and unresolved gaps

## Step 5: Synthesis Rules

1. Start from risk and threat path, not tool preference.
2. Prefer compensating-control discussion when ideal controls are not feasible.
3. Tie controls to operability (ownership, runbooks, alert triage, drills).
4. Keep findings falsifiable by naming evidence that could disprove them.
5. Prioritize remediations by risk reduction and implementation feasibility.

## Step 6: Validation and Rollout

Include:
- Validation checks for each high-priority remediation
- Sequencing (quick wins vs structural fixes)
- Rollback/safety guidance for high-impact changes

## Completion Criteria

A response is complete only if it includes:
1. Source coverage summary
2. Evidence-graded findings/recommendations
3. Explicit residual risks and assumptions
4. Validation plan and owner-oriented actions
