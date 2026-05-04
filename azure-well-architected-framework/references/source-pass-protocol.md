# Source Pass Protocol (Mandatory)

Use this protocol whenever producing non-trivial guidance with this skill.

## Objective

Prevent shallow Well-Architected recommendations by enforcing explicit source coverage and evidence quality.

## Step 1: Scope the Assessment

Capture:
- Workload type and critical business outcomes
- Environment scope (dev/test/prod; single/multi-region)
- Primary concern (reliability, security, cost, operations, performance)
- Dominant services in scope (for service-guide loading)

## Step 2: Canonical Source Sweep

Read `source-index.md` and cover each relevant section from `source-coverage-matrix.md`.

Minimum for full architecture recommendations:
- Pillars and core design context
- Architect role pages
- Reliability set
- Security set
- Cost optimization set
- Operational excellence set
- Performance efficiency set
- Relevant design guides
- Relevant service guides for in-scope services

## Step 3: Evidence Grading

For every major recommendation, mark evidence quality:
- `Verified`: directly supported by canonical source content.
- `Derived`: inferred by combining multiple verified sources.
- `Assumption`: not directly supported; requires explicit validation.

Never present assumptions as verified guidance.

## Step 4: Coverage Report

Return a concise report:
- Sections read
- Sections intentionally skipped (with reason)
- Service guides included/excluded and rationale
- Source ambiguities or unresolved details

## Step 5: Synthesis Discipline

1. Start from business requirements, not technology preference.
2. Evaluate cross-pillar consequences for each major decision.
3. Make reliability and security design concrete with flow and failure analysis.
4. Use cost and operations recommendations with measurable outcomes and owners.
5. Use service guides to sharpen implementation-level guidance when services are known.
6. Document tradeoffs and accepted risks explicitly.

## Step 6: Validation and Rollout

Include:
- Pre-production validation (tests, drills, performance/failure exercises)
- Operational readiness gates (observability, runbooks, ownership)
- Rollout/rollback strategy

## Completion Criteria

A response is complete only if it includes:
1. Source coverage summary
2. Evidence-graded recommendations
3. Explicit tradeoffs and residual risks
4. Validation and rollback plan
