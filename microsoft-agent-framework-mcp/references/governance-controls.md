# Governance Controls

## Access Model

- Default deny for all MCP tools.
- Grant least privilege at tool and server scope.
- Separate identities for read and write operations.
- Rotate credentials and avoid long-lived secrets where possible.

## Safety Controls

- Require approval for destructive or financial-impact actions.
- Enforce parameter validation before execution.
- Sanitize prompt/tool injection attempts from upstream inputs.
- Cap iteration/tool-call depth to prevent runaway loops.

## Audit and Compliance

Capture per call:
- Caller identity and policy context.
- Tool name and server endpoint.
- Input/output hash or redacted payload summary.
- Outcome, latency, and retry/failure metadata.

## Change Management

- Version tool schemas and prompt contracts.
- Stage rollout (dev -> preprod -> prod).
- Define rollback for policy and routing changes.
