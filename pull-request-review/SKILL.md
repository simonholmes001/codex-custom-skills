---
name: pull-request-review
description: Perform rigorous pull request reviews with a security-first, risk-based approach. Use when reviewing code changes, architecture changes, infrastructure/IaC updates, tests, migrations, CI/CD workflows, or release-impacting behavior. Prioritize actionable findings with severity, concrete evidence, and clear remediation.
metadata:
  category: engineering-practice
  subdomain: delivery-quality
  owner: custom
---

# Pull Request Review

Review pull requests to prevent defects, regressions, and security incidents while preserving delivery speed.

## Review Workflow

1. Establish scope and risk quickly.
- Read PR title/description, linked issues, changed files, and test evidence.
- Identify risk multipliers: auth, secrets, billing, data deletion, migration, networking, infra, concurrency, or public API changes.
- Adjust review depth to risk. High-risk changes require deep path-by-path validation.

2. Validate behavior before style.
- Confirm the implementation satisfies requirements and does not silently alter expected behavior.
- Trace critical execution paths end to end, including error paths and retries/timeouts.
- Treat missing negative-path handling as a defect.

3. Review by risk domains.
- Use `references/checklist.md` as the default checklist.
- For each domain, collect concrete evidence from code, tests, and configuration.
- Escalate severity using `references/severity-model.md`.

4. Validate test strategy quality.
- Verify tests prove the intended behavior and protect against regression.
- Require coverage for edge/error cases on high-risk paths.
- Flag flaky, overly mocked, or non-deterministic tests as quality risks.

5. Verify operational safety.
- Confirm observability (logs/metrics/traces), rollout safety, and backward compatibility.
- Validate migration and deployment safety (ordering, reversibility, blast radius).
- Ensure failure modes are explicit and diagnosable.

6. Produce review output.
- List findings first, ordered by severity (Critical -> High -> Medium -> Low).
- Include file and line references, impact, and a concrete remediation path.
- Keep summary short and only after findings.
- If no findings exist, state this explicitly and note any residual risk/testing gaps.

## Findings Format

Use this structure for each finding:

- `Severity`: Critical|High|Medium|Low
- `Title`: Short, specific defect statement
- `Evidence`: File/line and factual behavior
- `Impact`: Why this matters (security, data loss, outage, regression, maintainability)
- `Fix`: Smallest safe change to address it

Use templates from `references/comment-templates.md`.

## Non-Negotiable Quality Rules

- Do not approve code that can leak secrets, bypass authorization, or corrupt/delete data unintentionally.
- Do not approve high-risk changes without meaningful automated tests.
- Do not treat style-only comments as blockers when correctness/security gaps exist.
- Do not report speculative concerns without code evidence.
- Do not mix unrelated feedback into one finding; keep each defect isolated and actionable.

## Escalation Heuristics

Raise severity when any of the following are true:
- User data or credentials can be exposed, modified, or deleted incorrectly.
- Authorization boundaries can be bypassed across users/tenants.
- Public contracts break without compatibility controls.
- Deployments can fail non-gracefully with weak rollback options.
- Monitoring is insufficient to detect and triage failures quickly.

## Resources

- `references/severity-model.md`: Severity definitions and merge guidance.
- `references/checklist.md`: Domain checklist for deep and consistent reviews.
- `references/comment-templates.md`: Reusable finding and summary templates.

## Cross-Skill Standards

Read and apply `references/cross-skill-standards.md` for:

- Evidence quality rubric (`Verified`, `Derived`, `Assumption`)
- Context-budget/loading policy
- Anti-pattern and handoff rules
- Source freshness policy
- Minimum output additions for non-trivial responses
