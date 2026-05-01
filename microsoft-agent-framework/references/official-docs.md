# Microsoft Agent Framework Official Docs

Use this curated source list when recommendations must align to Microsoft guidance and project-maintained references.

## Validation Metadata

- Last reviewed: 2026-05-01
- Runtime focus: C# pivots where available
- Evidence levels:
1. `Verified`: directly visible in Microsoft Learn/API pages during curation.
2. `Partial`: page/topic indexed but some details access-limited in crawler.
3. `Derived`: implementation guidance inferred from verified docs and framework patterns.

## Core Product Docs

- Documentation landing: https://learn.microsoft.com/en-us/agent-framework/ (`Verified`)
- Overview (C# pivot): https://learn.microsoft.com/en-us/agent-framework/overview/?pivots=programming-language-csharp (`Verified`)
- Get started tutorial index: https://learn.microsoft.com/en-us/agent-framework/get-started/ (`Verified`)

## C# Get Started (Current Path)

- Step 1: Your First Agent: https://learn.microsoft.com/en-us/agent-framework/get-started/your-first-agent?pivots=programming-language-csharp
- Step 2: Add Tools: https://learn.microsoft.com/en-us/agent-framework/get-started/add-tools?pivots=programming-language-csharp
- Step 3: Multi-Turn Conversations: https://learn.microsoft.com/en-us/agent-framework/get-started/multi-turn?pivots=programming-language-csharp
- Step 4: Memory & Persistence: https://learn.microsoft.com/en-us/agent-framework/get-started/memory?pivots=programming-language-csharp
- Step 5: Workflows: https://learn.microsoft.com/en-us/agent-framework/get-started/workflows?pivots=programming-language-csharp
- Step 6: Host Your Agent: https://learn.microsoft.com/en-us/agent-framework/get-started/hosting?pivots=programming-language-csharp

## Agents Deep Dives

- Agents overview/types (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/?pivots=programming-language-csharp
- Running agents (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/running-agents?pivots=programming-language-csharp
- Agent pipeline architecture (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/agent-pipeline?pivots=programming-language-csharp
- Multimodal agents (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/multimodal?pivots=programming-language-csharp
- Structured outputs (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/structured-outputs?pivots=programming-language-csharp
- Background responses (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/background-responses?pivots=programming-language-csharp
- RAG (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/rag?pivots=programming-language-csharp
- Declarative agents (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/declarative?pivots=programming-language-csharp
- Agent skills (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/skills?pivots=programming-language-csharp
- CodeAct (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/code_act?pivots=programming-language-csharp

## Conversations Deep Dives

- Conversations overview (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/conversations/?pivots=programming-language-csharp
- Sessions (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/conversations/session?pivots=programming-language-csharp
- Context providers (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/conversations/context-providers?pivots=programming-language-csharp
- Storage (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/conversations/storage?pivots=programming-language-csharp
- Conversation compaction (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/conversations/compaction?pivots=programming-language-csharp

## Middleware Deep Dives

- Middleware overview (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/middleware/?pivots=programming-language-csharp
- Defining middleware (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/middleware/defining-middleware?pivots=programming-language-csharp
- Chat middleware (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/middleware/chat-middleware?pivots=programming-language-csharp
- Agent vs run scope (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/middleware/agent-vs-run-scope?pivots=programming-language-csharp
- Termination middleware (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/middleware/termination?pivots=programming-language-csharp

## Providers Deep Dives

- Providers overview (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/providers/?pivots=programming-language-csharp
- OpenAI provider (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/providers/openai?tabs=oai-config-chat-completion&pivots=programming-language-csharp
- Anthropic provider (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/providers/anthropic?pivots=programming-language-csharp
- GitHub Copilot provider (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/providers/github-copilot?pivots=programming-language-csharp
- Agent-to-agent provider (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/providers/agent-to-agent?pivots=programming-language-csharp
- Custom provider (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/providers/custom?pivots=programming-language-csharp

## Workflows Deep Dives

- Workflows overview: https://learn.microsoft.com/en-us/agent-framework/workflows/
- Executors (C# pivot): https://learn.microsoft.com/en-us/agent-framework/workflows/executors?pivots=programming-language-csharp
- Edges (C# pivot): https://learn.microsoft.com/en-us/agent-framework/workflows/edges?pivots=programming-language-csharp
- Events (C# pivot): https://learn.microsoft.com/en-us/agent-framework/workflows/events?pivots=programming-language-csharp
- Workflows core concepts (C# pivot): https://learn.microsoft.com/en-us/agent-framework/workflows/workflows?pivots=programming-language-csharp
- Agents in workflows (C# pivot): https://learn.microsoft.com/en-us/agent-framework/workflows/agents-in-workflows?pivots=programming-language-csharp
- Human in the loop (C# pivot): https://learn.microsoft.com/en-us/agent-framework/workflows/human-in-the-loop?pivots=programming-language-csharp
- Workflow state (C# pivot): https://learn.microsoft.com/en-us/agent-framework/workflows/state?pivots=programming-language-csharp
- Checkpoints (C# pivot): https://learn.microsoft.com/en-us/agent-framework/workflows/checkpoints?tabs=py-ckpt-inmemory&pivots=programming-language-csharp
- Declarative workflows (C# pivot): https://learn.microsoft.com/en-us/agent-framework/workflows/declarative?pivots=programming-language-csharp
- Workflow observability (C# pivot): https://learn.microsoft.com/en-us/agent-framework/workflows/observability?pivots=programming-language-csharp
- As-agents bridge (C# pivot): https://learn.microsoft.com/en-us/agent-framework/workflows/as-agents?pivots=programming-language-csharp
- Visualization (C# pivot): https://learn.microsoft.com/en-us/agent-framework/workflows/visualization?pivots=programming-language-csharp

## Workflow Orchestrations

- Orchestrations overview: https://learn.microsoft.com/en-us/agent-framework/workflows/orchestrations/
- Sequential orchestration (C# pivot): https://learn.microsoft.com/en-us/agent-framework/workflows/orchestrations/sequential?pivots=programming-language-csharp
- Concurrent orchestration (C# pivot): https://learn.microsoft.com/en-us/agent-framework/workflows/orchestrations/concurrent?pivots=programming-language-csharp
- Handoff orchestration (C# pivot): https://learn.microsoft.com/en-us/agent-framework/workflows/orchestrations/handoff?pivots=programming-language-csharp
- Group chat orchestration (C# pivot): https://learn.microsoft.com/en-us/agent-framework/workflows/orchestrations/group-chat?pivots=programming-language-csharp

## Advanced Workflows

- Agent executor (C# pivot): https://learn.microsoft.com/en-us/agent-framework/workflows/advanced/agent-executor?pivots=programming-language-csharp
- Execution modes (C# pivot): https://learn.microsoft.com/en-us/agent-framework/workflows/advanced/execution-modes?pivots=programming-language-csharp
- Resettable executors (C# pivot): https://learn.microsoft.com/en-us/agent-framework/workflows/advanced/resettable-executors?pivots=programming-language-csharp
- Sub-workflows (C# pivot): https://learn.microsoft.com/en-us/agent-framework/workflows/advanced/sub-workflows?pivots=programming-language-csharp

## A2A Hosting and Integration

- A2A hosting: https://learn.microsoft.com/en-us/agent-framework/hosting/agent-to-agent
- A2A integration (C# pivot): https://learn.microsoft.com/en-us/agent-framework/integrations/a2a?tabs=dotnet-cli%2Cuser-secrets&pivots=programming-language-csharp

## .NET API Surface

- `Microsoft.Agents.AI` namespace API docs: https://learn.microsoft.com/en-us/dotnet/api/microsoft.agents.ai?view=agent-framework-dotnet-latest

## Journey Guides

- Adding tools: https://learn.microsoft.com/en-us/agent-framework/journey/adding-tools
- Adding skills: https://learn.microsoft.com/en-us/agent-framework/journey/adding-skills
- Adding middleware: https://learn.microsoft.com/en-us/agent-framework/journey/adding-middleware
- Adding context providers: https://learn.microsoft.com/en-us/agent-framework/journey/adding-context-providers
- Agents as tools: https://learn.microsoft.com/en-us/agent-framework/journey/agents-as-tools
- Journey: agent-to-agent: https://learn.microsoft.com/en-us/agent-framework/journey/agent-to-agent
- Journey: workflows: https://learn.microsoft.com/en-us/agent-framework/journey/workflows

## Tools Deep Dives

- Tools overview (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/tools/?pivots=programming-language-csharp
- Function tools (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/tools/function-tools?pivots=programming-language-csharp
- Tool approvals / HITL (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/tools/tool-approval?pivots=programming-language-csharp
- Code interpreter tool (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/tools/code-interpreter?pivots=programming-language-csharp
- File search tool (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/tools/file-search?pivots=programming-language-csharp
- Web search tool (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/tools/web-search?pivots=programming-language-csharp
- Hosted MCP tools (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/tools/hosted-mcp-tools?pivots=programming-language-csharp
- Local MCP tools (C# pivot): https://learn.microsoft.com/en-us/agent-framework/agents/tools/local-mcp-tools?pivots=programming-language-csharp

## Microsoft Architecture Guidance

- AI agent design patterns: https://learn.microsoft.com/en-us/azure/architecture/ai-ml/guide/ai-agent-design-patterns

## Repository and Source of Truth

- GitHub repository: https://github.com/microsoft/agent-framework
- Repository README (raw): https://raw.githubusercontent.com/microsoft/agent-framework/main/README.md

## Background and Positioning

- Announcement blog: https://devblogs.microsoft.com/foundry/introducing-microsoft-agent-framework-the-open-source-engine-for-agentic-ai-apps/

## Related Exploration Paths

- Migration from Semantic Kernel: https://learn.microsoft.com/en-us/agent-framework/migration-guide/from-semantic-kernel
- Migration from AutoGen: https://learn.microsoft.com/en-us/agent-framework/migration-guide/from-autogen
