# Tools Guidance (C#-oriented)

Use this when choosing, configuring, and governing tools for Microsoft Agent Framework agents.

## Tool Selection Order

1. Function tools for deterministic host logic.
2. Provider-hosted tools (code interpreter, file search, web search) when model-side capability is required.
3. MCP tools (hosted or local) for external system integration with explicit boundaries.

Prefer the least-privileged and simplest option that solves the requirement.

## Function Tools

- Define precise parameter schemas and descriptions; tool quality depends heavily on contract clarity.
- Keep functions idempotent when possible and return compact, machine-usable outputs.
- Add validation and error normalization so agent loops can recover predictably.

## Tool Approval (Human-in-the-loop)

- Require approvals for sensitive operations (data exfiltration, payments, mutations, privileged actions).
- Preserve approval context (requested tool, arguments, rationale, user decision) in audit logs.
- Design re-entry flows so runs can continue with full context after approval/denial.

## Code Interpreter

- Use for computational/analysis tasks where generated code execution is valuable.
- Treat runtime execution as high risk: set quotas/timeouts and control artifact handling.
- Define policy for generated files and output retention.

## File Search

- Use for document-grounded Q&A when provider supports hosted vector search.
- Track ingestion lifecycle (upload, index, cleanup) and data residency/compliance requirements.
- Add fallback behavior for missing documents or retrieval failures.

## Web Search

- Use for freshness-sensitive questions where static knowledge is insufficient.
- Bound web-search usage by policy (domain allowlist, citation requirements, result filtering).
- For regulated contexts, require provenance capture before acting on web-derived claims.

## MCP Tools (Hosted and Local)

- Hosted MCP: provider-managed server wiring; useful for centralized governance and shared capability.
- Local MCP: direct local server/client integration; gives more control over transport and runtime.
- In both modes:
1. Restrict server list and tool allowlist.
2. Set approval policy (`never`/`always`/custom) per risk.
3. Dispose connections/resources reliably.
4. Monitor latency/errors per MCP server.

## Credential and Runtime Safety

- `DefaultAzureCredential` is acceptable for local development; prefer explicit production credentials (for example managed identity).
- Scope permissions per tool/provider and separate dev/test/prod identities.
- Add telemetry for tool-call counts, failures, approval waits, and retry storms.
