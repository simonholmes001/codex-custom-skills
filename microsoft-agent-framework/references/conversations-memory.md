# Conversations, Sessions, and Memory (C#-oriented)

Use this guide when designing long-running, multi-turn agent interactions.

## Conversation Model

- Treat conversations as durable execution context, not only message history.
- Use sessions to preserve continuity across turns, tool calls, and resumptions.
- Keep explicit identifiers for conversation/session/thread in app state for traceability.

## Sessions

- Use session APIs as the primary continuity mechanism for multi-turn scenarios.
- Persist session identifiers and lifecycle metadata (created, last active, status).
- Add timeout and expiry policies for abandoned sessions.

## Context Providers

- Use context providers to inject relevant external state at run time.
- Keep providers focused and composable (for example user profile, business state, prior artifacts).
- Order providers intentionally because composition order can influence final prompt/context payload.
- Cache expensive provider fetches with bounded TTL where correctness allows it.

## Storage

- Choose storage based on durability and scale requirements:
1. In-memory for local dev/tests only.
2. Persistent store for production (database/object storage as appropriate).
- Version serialized conversation/session payloads to support schema evolution.
- Encrypt sensitive content at rest and apply retention/deletion policies.

## Compaction

- Use compaction to control token growth and latency in long conversations.
- Keep compaction policies explicit:
1. Trigger threshold (message count/token count/time window).
2. Strategy (summarize, prune, preserve critical facts).
3. Recovery path when summaries are low quality.
- Preserve critical invariants (user commitments, approvals, identifiers) outside lossy summaries.

## Operational Guidance

- Emit telemetry for session churn, compaction frequency, context provider latency, and token trends.
- Add fallback behavior for missing context sources.
- Validate that compaction does not break downstream tool execution assumptions.
