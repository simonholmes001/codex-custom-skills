# MAF + MCP Architecture Notes

## Logical Components

Typical topology includes:
- Client/application entrypoint.
- MAF runtime (agent(s), planner/manager, middleware).
- MCP client adapter layer for tool transport.
- One or more MCP servers exposing scoped tools.
- Data/control systems behind those tools.

## Trust Boundaries

Define and document:
1. Agent runtime boundary (prompt + memory + middleware).
2. MCP transport boundary (request/response integrity and timeout handling).
3. Tool execution boundary (read-only vs mutating operations).
4. Credential boundary (which identity can call which tool set).

## Recommended Separation

- Keep planning/reasoning separate from tool execution policy.
- Isolate high-risk mutating tools into dedicated MCP servers.
- Prefer explicit routing rules over free-form autonomous tool selection in production-critical paths.

## Data Handling

- Validate MCP outputs against expected schema before downstream use.
- Redact sensitive fields before logging.
- Define retention and replay policy for tool-call traces.
