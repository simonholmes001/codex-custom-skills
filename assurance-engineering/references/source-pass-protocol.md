# Source Pass Protocol (Mandatory)

Use this protocol whenever producing non-trivial assurance conclusions.

## Objective

Prevent unsupported assurance judgments by enforcing source coverage, evidence-quality grading, and explicit uncertainty handling.

## Step 1: Scope and Stakes

Capture:
- Workload boundary and critical assets
- Business impact of control failure
- Regulatory/compliance constraints
- Assessment type (readiness, gap assessment, post-incident, periodic review)

## Step 2: Canonical Source Sweep

Read `source-index.md` and cover each relevant section from `source-coverage-matrix.md`.

Minimum for full assurance assessments:
- Security baseline guidance
- Operational excellence guidance
- AI security guidance (when AI scope exists)

## Step 3: Evidence Grading

For each major conclusion, mark:
- `Verified`: directly supported by source content and evidence artifacts.
- `Derived`: reasoned from multiple verified signals.
- `Assumption`: not validated; requires follow-up evidence.

Never present assumptions as verified findings.

## Step 4: Coverage Report

Return:
- Sections read
- Sections intentionally skipped (with reason)
- Ambiguities and unresolved evidence gaps

## Step 5: Assessment Discipline

1. Evaluate both control design and operating effectiveness.
2. Distinguish missing controls from missing evidence.
3. Make compensating controls explicit.
4. Score residual risk after existing controls, not before.
5. Keep recommendations owner-actionable and testable.

## Step 6: Validation and Closure

For each high-priority remediation:
- Define acceptance evidence
- Define validation test/check
- Define owner and target timeline

## Completion Criteria

A response is complete only if it includes:
1. Source coverage summary
2. Evidence-graded findings
3. Residual risk and confidence levels
4. Remediation backlog and evidence closure plan
