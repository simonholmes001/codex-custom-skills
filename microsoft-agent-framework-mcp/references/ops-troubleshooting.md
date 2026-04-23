# Ops and Troubleshooting

Use this sequence for incident triage.

## 1. Confirm Intent and Scope

- Which agent, session, and tool call failed?
- Is failure isolated to one MCP server or broad?

## 2. Check Transport and Availability

- MCP server reachable and healthy.
- Timeout and retry behavior aligned with SLO.
- Rate limit and quota posture.

## 3. Validate Contract Compatibility

- Tool exists with expected name/version.
- Input schema still matches caller payload.
- Output parsing/validation logic still valid.

## 4. Inspect Auth and Policy

- Identity token/credential validity.
- RBAC/policy denial events.
- Approval state for sensitive operations.

## 5. Remediate and Verify

- Apply smallest safe fix first.
- Re-run targeted scenario.
- Confirm traces, metrics, and audit continuity.

## Signals to Track

- Tool call success rate.
- p50/p95/p99 tool latency.
- Retry count and terminal error codes.
- Approval queue time for gated actions.
