# Security and Governance

## Minimum Baseline

- Default-deny all server/tool access.
- Explicitly allow only required tools by environment.
- Separate read-only and mutating permissions.
- Use short-lived credentials and managed identities where available.

## Data and Prompt Safety

- Treat tool output as untrusted input until validated.
- Redact sensitive fields in logs and traces.
- Block prompt injection attempts from tool content before reuse.

## Policy Controls

- Require approvals for destructive or financial-impact actions.
- Version tool contracts and routing rules.
- Record exemptions with owner, reason, and expiry.

## Audit Requirements

Per call, capture:
- Caller identity and policy context.
- Server/tool invoked.
- Input/output summary (redacted/hash as needed).
- Latency, retry count, and terminal status.
