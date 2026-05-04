# Source Pass Protocol (Mandatory)

Use this protocol whenever producing non-trivial guidance with this skill.

## Goal

Prevent shallow recommendations by forcing explicit source coverage, evidence grading, and traceability.

## Step 1: Scope and Runtime

Capture:
- Target runtime (.NET, Python, mixed)
- Deployment shape (local, container, Azure)
- Problem type (greenfield, migration, hardening, incident/troubleshooting)

## Step 2: Canonical Source Sweep

Read `official-docs.md`, then process every topic bucket in `source-coverage-matrix.md` relevant to the request.

Minimum for architecture guidance:
- Core product docs
- Get-started path
- Agents + tools + providers
- Workflows + orchestrations
- Conversations/memory
- Middleware
- Production and migration references

## Step 3: Evidence Grading

For each major recommendation, tag evidence quality:
- `Verified`: directly supported by canonical source text.
- `Derived`: inferred from multiple verified sources.
- `Assumption`: not confirmed in sources; requires validation.

Never present assumptions as facts.

## Step 4: Coverage Log

Return a compact coverage report:
- Sections read
- Sections intentionally skipped
- Gaps due to unavailable or ambiguous source details

## Step 5: Synthesis Rules

1. Start from the smallest viable architecture.
2. Add complexity only when justified by requirements.
3. Separate deterministic workflow concerns from agentic concerns.
4. Make risk boundaries explicit for external tools, MCP, and A2A calls.
5. Include observability and approval controls as first-class design elements.

## Step 6: Validation and Rollout

Before final recommendation, include:
- Functional validation approach
- Operational readiness checks (telemetry, retries, runbooks)
- Change safety plan (phased rollout + rollback)

## Completion Criteria

A response is complete only if it includes:
1. Source coverage summary.
2. Evidence-graded recommendations.
3. Explicit assumptions and unresolved risks.
4. Validation and rollback guidance.
