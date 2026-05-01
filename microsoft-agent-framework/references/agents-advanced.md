# Advanced Agent Capabilities (C#-oriented)

Use this guide when user asks go beyond a basic single-agent flow.

## Agent Pipeline Architecture

- Treat `AIAgent` execution as layered:
1. Agent middleware/decorators.
2. Context resolution (history + context providers).
3. Chat client middleware/provider call.
- Prefer placing cross-cutting policy (logging, redaction, validation, safety) in middleware, not prompt text.
- Keep context providers composable and ordered intentionally because provider order affects final request shape.

## Background Responses

- Use background responses for long-running generation or when client connectivity may be interrupted.
- In C#, set `AllowBackgroundResponses = true` via run options and persist session + latest update IDs so you can resume/poll reliably.
- Add explicit timeout, cancellation, and user-facing status reporting for background runs.

## Structured Outputs

- Use structured outputs when downstream steps require schema-constrained data.
- Prefer typed schemas for compile-time safety when output shape is known; use JSON-schema style when shape is dynamic.
- Validate and handle partial/invalid output paths explicitly; do not assume perfect conformance.
- For streaming runs, finalize and parse structured result after stream completion.

## Multimodal Inputs

- Design instructions and tool contracts assuming mixed content (text + files/images/audio/video where provider supports it).
- Check provider capability and model compatibility before enabling multimodal paths.
- Add file-size/type guardrails and privacy review before forwarding external media to model providers.

## RAG Patterns

- Keep retrieval and generation concerns separated:
1. Retrieval index construction and freshness strategy.
2. Query-time retrieval function/tool.
3. Citation/grounding policy in agent instructions.
- Favor hybrid retrieval and metadata filtering where available.
- Add safeguards for empty/low-confidence retrieval and fallback behavior.

## Declarative Agents

- Use declarative YAML when teams need reviewable, versioned agent configuration separate from code.
- Keep environment bindings explicit (model id, endpoint, auth source) and validate at startup.
- Use declarative config for stable defaults; keep runtime overrides deliberate and auditable.

## Agent Skills

- Use skills providers to expose reusable capabilities as discoverable, scoped skill packs.
- Treat skills as governed interfaces: clear descriptions, bounded parameters, explicit side effects.
- Avoid unbounded skill discovery in production; curate skill directories and review changes.

## CodeAct

- Use CodeAct when tasks benefit from iterative code execution/planning loops inside a sandbox.
- Keep host-exposed tools minimal; even with sandboxing, `call_tool(...)` reaches host process tools.
- Prefer strict sandbox defaults and explicit network/filesystem allowances only when required.
- For simple one-tool calls, use direct tools instead of introducing CodeAct overhead.
