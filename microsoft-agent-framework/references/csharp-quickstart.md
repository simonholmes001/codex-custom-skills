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

For general framework + Foundry paths, repository docs also show:

```bash
dotnet add package Microsoft.Agents.AI
# or Foundry-specific package variants when needed
```

## Minimal Agent Shape

A typical C# flow is:
1. Instantiate provider client (Azure OpenAI/Foundry/OpenAI).
2. Convert provider client to `AIAgent`.
3. Set model name + instructions.
4. Run prompt with `RunAsync`.

## Practical Implementation Notes

- Keep model/deployment names and endpoints in environment variables.
- Prefer managed credentials/RBAC in production.
- Add logging and telemetry at the first runnable milestone.
- Put hard limits on loop depth and tool retries.
