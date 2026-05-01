# Providers Guidance (C#-oriented)

Use this guide to select and configure model/providers for Microsoft Agent Framework.

Evidence level: `Partial` for provider-specific setup details; `Derived` for cross-provider architecture guidance.

## Provider Selection Heuristic

1. Start with a provider already approved in your org.
2. Match provider capability to requirement (tools, multimodal, latency, cost, region).
3. Keep provider-specific wiring isolated so agent logic stays portable.

## Common Provider Model

- Keep a stable internal abstraction around:
1. Credentials and endpoint config.
2. Model selection and run options.
3. Streaming vs non-streaming execution.
4. Tool and structured-output capability checks.

## OpenAI Provider

- Use explicit model/deployment configuration and runtime options per environment.
- Separate local-dev credentials from production credentials.
- Validate capability compatibility (for example structured outputs/tools) for the selected model.

```csharp
// Sketch: provider -> AIAgent conversion with explicit model/instructions.
var endpoint = new Uri(builder.Configuration["AZURE_AI_PROJECT_ENDPOINT"]!);
var project = new Azure.AI.Projects.AIProjectClient(endpoint, new Azure.Identity.DefaultAzureCredential());
var agent = project.AsAIAgent(
    model: builder.Configuration["AZURE_AI_MODEL"] ?? "gpt-4o-mini",
    instructions: "You are a reliable assistant.",
    name: "assistant");
```

## Anthropic Provider

- Treat Anthropic integration as provider-specific adapter configuration behind the same `AIAgent` usage pattern.
- Validate tool/streaming behavior parity before production rollout.

## GitHub Copilot Provider

- Use when enterprise policy and developer workflow align with Copilot-backed execution.
- Confirm tenant/org controls, identity boundaries, and data handling requirements early.

## Agent-to-Agent Provider

- Use A2A when composing remote agents as capabilities across service boundaries.
- Treat remote agents as external dependencies:
1. AuthN/AuthZ boundary.
2. Contract/version compatibility.
3. Latency/retry/fallback behavior.

## Custom Provider

- Use custom providers when standard adapters cannot satisfy requirements.
- Keep custom provider contracts narrow and heavily tested (request mapping, response mapping, errors, streaming).
- Provide deterministic fallback behavior when custom provider paths fail.

## Operational Guidance

- Emit provider-level telemetry (latency, error rate, throttling, token usage, cost indicators).
- Add capability discovery checks at startup and fail fast on unsupported modes.
- Keep per-provider feature flags for controlled rollout and quick rollback.
