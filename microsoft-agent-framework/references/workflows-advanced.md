# Advanced Workflows (C#-oriented)

Use this guide for complex execution and composition scenarios.

## Agent Executor

- Use agent executors when a workflow node needs LLM-driven planning/tool use.
- Keep deterministic graph routing outside the agent executor whenever possible.
- Add hard limits for tool calls, iterations, and node runtime.

## Execution Modes

- Choose execution mode based on correctness and latency needs:
1. Synchronous/foreground for interactive responses.
2. Background or resumable modes for long-running processing.
- Make run mode explicit in architecture docs and telemetry labels.

## Resettable Executors

- Use resettable executors when retries require safe state rewind.
- Define reset boundaries:
1. What state is cleared.
2. What state is preserved (IDs, audit artifacts, approvals).
- Verify idempotency of side-effecting steps before enabling reset/replay.

## Sub-workflows

- Use sub-workflows to encapsulate reusable, bounded logic.
- Keep sub-workflow interfaces narrow and typed.
- Version sub-workflow contracts to avoid breaking parents.

## Reliability Pattern

- Pair advanced execution with checkpoints, dead-letter handling, and deterministic recovery paths.
- Test failure injection at workflow and sub-workflow boundaries.
