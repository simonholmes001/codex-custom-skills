---
name: twelve-factor-app
description: Assess, design, and remediate applications against the Twelve-Factor App principles for cloud-native delivery. Use when Codex needs to review a service's operational readiness, propose architecture or code changes for stateless/process-based execution, improve config and secret handling, standardize logs and release/run separation, or produce a concrete 12-factor gap analysis with prioritized fixes.
metadata:
  category: architecture-design
  subdomain: cloud-native
  owner: custom
---

# Twelve Factor App

## Overview

Use this skill to run a practical 12-factor assessment and convert findings into specific engineering actions. Prefer concrete evidence from repo files, deployment manifests, and runtime configuration over generic recommendations.

## Workflow

1. Determine scope.
2. Collect evidence.
3. Score all 12 factors.
4. Prioritize remediation.
5. Deliver implementation-ready changes.

## 1) Determine Scope

Capture:
- runtime and language (`dotnet`, `node`, `python`, etc.)
- deploy target (containers, PaaS, VM, Kubernetes)
- critical services (database, queue, cache, object storage)
- constraints (security, compliance, migration window)

If scope is unclear, state assumptions explicitly and continue.

## 2) Collect Evidence

Inspect only what is necessary:
- dependency and build metadata (`package.json`, `*.csproj`, `requirements*.txt`, `Dockerfile`)
- runtime config and infra (`.env*`, Helm charts, Terraform, compose/k8s manifests)
- startup and process model (entrypoints, worker definitions, web binding)
- observability and ops hooks (logging config, health endpoints, runbooks)

Use the checklist at `references/twelve-factor-checklist.md` as the canonical factor-by-factor rubric.

## 3) Score All 12 Factors

For each factor, report:
- status: `meets`, `partial`, or `gap`
- evidence: file/path/config proving the status
- impact: delivery, reliability, security, or operability consequence
- fix: smallest viable change that closes the gap

## 4) Prioritize Remediation

Prioritize by:
- production risk first (secrets, statefulness, non-disposable startup)
- blast radius second (shared platform/runtime concerns)
- delivery velocity third (changes that unblock CI/CD and parity)

Prefer staged plans:
1. immediate hardening (hours to days)
2. structural refactors (days to weeks)
3. platform optimization (longer-term)

## 5) Deliver Implementation-Ready Changes

When asked to implement:
- change the minimal file set needed for the selected factors
- keep behavior stable unless the factor fix requires behavior change
- add or update tests for config loading, process startup, and dependency wiring
- validate with existing test/build commands when available

## Output Contract

Return results in this order:
1. `Assessment Summary` with score (`x/12` fully met)
2. `Factor Findings` (1..12)
3. `Prioritized Remediation Plan`
4. `Concrete File Changes` (if code edits were requested)
5. `Residual Risks / Assumptions`

## References

- Read `references/twelve-factor-checklist.md` when performing assessments.

## Cross-Skill Standards

Read and apply `references/cross-skill-standards.md` for:

- Evidence quality rubric (`Verified`, `Derived`, `Assumption`)
- Context-budget/loading policy
- Anti-pattern and handoff rules
- Source freshness policy
- Minimum output additions for non-trivial responses
