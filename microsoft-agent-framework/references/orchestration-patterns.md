# Orchestration Pattern Selection

This guide summarizes Microsoft architecture guidance for multi-agent pattern selection.

## Start with Lowest Complexity

Choose the minimum level that can meet reliability and quality goals:
1. Direct model call.
2. Single agent with tools.
3. Multi-agent orchestration.

Move to multi-agent only when single-agent complexity, tool overload, or security boundaries require it.

## Sequential Orchestration

Use when:
- Work is a linear pipeline with strict stage dependencies.
- Progressive refinement is needed (draft -> review -> polish).

Avoid when:
- Stages are parallelizable.
- You need dynamic routing or backtracking loops.

## Concurrent Orchestration

Use when:
- Multiple specialist perspectives are needed in parallel.
- Latency benefits from fan-out/fan-in processing.

Avoid when:
- Stages must build on prior outputs in sequence.
- Conflicting outputs have no clear reconciliation strategy.

## Group Chat Orchestration

Use when:
- Collaborative debate or maker-checker loops improve quality.
- You need transparent shared-thread decision history.

Avoid when:
- Deterministic workflows are sufficient.
- Conversation overhead is too costly for real-time paths.

## Handoff and Dynamic Manager Patterns

Use handoff when:
- Responsibility should transfer between specialists over time.

Use manager-led dynamic planning (for example ledger-style manager patterns) when:
- Task decomposition changes as new evidence arrives.
- The plan must be continuously revised with auditable checkpoints.

## Pattern Selection Heuristic

1. Can one agent with tools solve it? Use single-agent.
2. Is the flow deterministic? Use workflow/sequential.
3. Need independent specialist analysis? Use concurrent.
4. Need debate/consensus/critic loops? Use group chat.
5. Need dynamic delegation and replanning? Use handoff or manager-led dynamic orchestration.
