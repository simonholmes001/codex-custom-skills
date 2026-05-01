# C# Quick Start Notes

## Prerequisites

- .NET SDK (8.0 or newer is commonly used in samples).
- Azure OpenAI or Azure AI Foundry project with a deployed model.
- Azure CLI installed and authenticated (`az login`) when using Azure CLI credentials.
- Appropriate Azure role assignments on target AI resources.

## Project Bootstrap

```bash
dotnet new console -o AgentFrameworkQuickStart
cd AgentFrameworkQuickStart
```

## Common Package Paths

For Azure OpenAI-based sample paths:

```bash
dotnet add package Azure.AI.OpenAI --prerelease
dotnet add package Azure.Identity
dotnet add package Microsoft.Agents.AI.OpenAI --prerelease
```

For Foundry/Azure AI Projects-based paths:

```bash
dotnet add package Azure.AI.Projects --prerelease
dotnet add package Azure.Identity
dotnet add package Microsoft.Agents.AI.Foundry --prerelease
```

## Minimal Agent Shape

A typical C# flow is:
1. Instantiate provider client (Azure OpenAI/Foundry/OpenAI).
2. Convert provider client to `AIAgent`.
3. Set model/deployment + instructions (+ optional `name`).
4. Run prompt with `RunAsync`.
5. Stream when needed with `RunStreamingAsync`.

## Stepwise Build-Up from Get Started

- Step 1 (`your-first-agent`): baseline single-turn invocation and streaming.
- Step 2 (`add-tools`): register function tools with `AIFunctionFactory.Create(...)`; tool metadata comes from `[Description]` attributes.
- Step 3 (`multi-turn`): maintain conversation continuity using sessions.
- Step 4 (`memory`): inject persistent context with context providers.
- Step 5 (`workflows`): compose deterministic multi-step execution with workflow executors.
- Step 6 (`hosting`): expose agents through hosting surfaces (for example ASP.NET Core with A2A adapter).

## Practical Implementation Notes

- Keep model/deployment names and endpoints in environment variables.
- `DefaultAzureCredential` is convenient for local development; for production, prefer explicit credentials (for example managed identity) and scoped RBAC.
- Agent Framework does not auto-load `.env`; load it explicitly if needed.
- Add logging and telemetry at the first runnable milestone.
- Put hard limits on loop depth and tool retries.
