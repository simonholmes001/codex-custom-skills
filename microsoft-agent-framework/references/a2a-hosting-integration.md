# A2A Hosting and Integration (C#-oriented)

Use this guide when exposing or consuming agents through the Agent-to-Agent protocol.

Evidence level: `Verified` for hosting package/components and endpoint mapping patterns from visible docs.

## Hosting via ASP.NET Core

- Use `Microsoft.Agents.AI.Hosting.A2A.AspNetCore` to expose `AIAgent` endpoints over A2A.
- Register agents as keyed services, then register keyed A2A servers.
- Map protocol endpoints and publish an agent card for discovery.

```csharp
// Minimal host sketch (package names/registration details may vary by prerelease).
builder.Services.AddKeyedSingleton<AIAgent>("weather-agent", (sp, _) => agent);
builder.AddA2AServer("weather-agent");
var app = builder.Build();
app.MapA2AHttpJson("weather-agent", "/a2a/weather-agent");
```

## Protocol Bindings

- Support HTTP+JSON and/or JSON-RPC bindings based on client compatibility requirements.
- If both are enabled, keep endpoint paths explicit and documented.

## Server Components and Overrides

- Default server wiring includes:
1. Agent handler.
2. Session store.
3. Task store.
4. Run mode.
- Replace in-memory defaults with durable stores for production.
- Override keyed components per agent when behavior/security requirements differ.

## Background and Tasks

- Decide whether background responses are allowed per hosted agent.
- Persist task state durably for resumable long-running operations.

## Multi-agent Hosts

- Host multiple agents in one process only if isolation boundaries are clear.
- Partition agent names, endpoints, and resource quotas to avoid noisy-neighbor effects.

## Security and Ops

- Treat A2A endpoint as an external API boundary: auth, rate limiting, and audit logging apply.
- Capture per-agent metrics: request rate, latency, task completion, and failure classes.
