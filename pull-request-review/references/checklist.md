# PR Review Checklist

Use this checklist as a default. Prioritize items by risk.

## 1) Correctness and Behavior
- Does code implement the stated requirement fully?
- Are edge cases and failure paths handled?
- Are retries/timeouts/backoff/cancellation coherent?
- Are defaults and fallbacks safe and explicit?

## 2) Security and Access Control
- Are authN/authZ checks enforced on every sensitive path?
- Is tenant/user isolation preserved?
- Are secrets/tokens excluded from logs/errors/commits?
- Are inputs validated and outputs sanitized where needed?

## 3) Data and Privacy
- Any risk of data loss/corruption/duplication?
- Are migrations safe, ordered, and reversible?
- Are retention/deletion rules correct and auditable?
- Is PII handled per policy and least exposure?

## 4) API and Contract Safety
- Are request/response contracts backward compatible?
- Are status codes and error contracts consistent?
- Are versioning and deprecation paths clear?
- Are breaking changes documented and gated?

## 5) Reliability and Performance
- Any new bottlenecks (N+1, unbounded loops, sync-over-async)?
- Are resource lifecycles safe (connections/files/memory)?
- Are concurrency assumptions explicit and correct?
- Are rate limits, quotas, and circuit-breakers considered?

## 6) Observability and Operability
- Are logs structured and actionable?
- Are critical metrics/traces emitted?
- Can operators detect and triage failures quickly?
- Are feature flags/rollout/rollback strategies defined?

## 7) Testing and Verification
- Do tests prove the intended behavior, not implementation details?
- Are high-risk code paths covered by integration/contract tests?
- Are negative paths and permission boundaries tested?
- Are tests deterministic and maintainable?

## 8) Maintainability
- Is naming clear and intent-revealing?
- Are abstractions justified and cohesive?
- Is duplication reduced without over-engineering?
- Is documentation updated where behavior changed?
