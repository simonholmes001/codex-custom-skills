# Source Pass Protocol (Mandatory)

Use this protocol whenever producing non-trivial guidance with this skill.

## Objective

Prevent shallow landing-zone guidance by enforcing explicit source coverage, evidence quality grading, and traceable design decisions.

## Step 1: Scope and Enterprise Context

Capture:
- Tenant and organization boundaries
- Compliance/data residency constraints
- Operating model (central platform vs federated)
- Region and connectivity requirements

## Step 2: Canonical Source Sweep

Read `official-docs.md` and cover each relevant section from `source-coverage-matrix.md`.

Minimum for full landing-zone recommendations:
- CAF overview and landing-zone fundamentals
- Design principles and design areas
- Deployment guidance
- ALZ implementation reference posture

## Step 3: Evidence Grading

For each major recommendation, mark:
- `Verified`: directly supported by canonical source content.
- `Derived`: inferred from multiple verified sources.
- `Assumption`: not directly supported; requires validation.

Never present assumptions as verified guidance.

## Step 4: Coverage Report

Return:
- Sections read
- Sections intentionally skipped (with reason)
- Source ambiguities and unresolved details

## Step 5: Synthesis Discipline

1. Start from operating model and constraints, not preferred topology.
2. Make management group and subscription boundaries explicit.
3. Define policy/guardrails before workload onboarding.
4. Document tradeoffs and exception-handling model.
5. Tie recommendations to validation gates and rollout safety.

## Step 6: Rollout and Validation

Include:
- Foundation-first sequencing
- Onboarding readiness checks
- Rollback/fallback for high-impact governance/network changes

## Completion Criteria

A response is complete only if it includes:
1. Source coverage summary
2. Evidence-graded design decisions
3. Explicit tradeoffs, assumptions, and residual risks
4. Phased rollout with validation and rollback criteria
