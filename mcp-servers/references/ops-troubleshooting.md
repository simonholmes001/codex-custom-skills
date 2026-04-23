# Ops and Troubleshooting

Use this sequence for reliable triage.

## 1. Scope and Impact

- Which client, server, and tool call is failing?
- Is impact isolated or widespread?

## 2. Connectivity and Health

- Server reachable and healthy.
- Transport/session negotiation stable.
- Latency within expected bounds.

## 3. Contract Compatibility

- Tool still exists with expected name/signature.
- Input schema matches current server expectations.
- Output parsing/validation still valid.

## 4. Auth and Authorization

- Credential/token validity.
- RBAC/policy denial events.
- Approval state for gated operations.

## 5. Remediation and Verification

- Apply smallest safe fix.
- Re-run targeted scenario.
- Confirm telemetry and audit continuity.

## Core Signals

- Tool success rate and error code distribution.
- p50/p95/p99 tool latency.
- Retry amplification rate.
- Approval queue duration for gated actions.
