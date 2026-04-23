# Integration Patterns

## Pattern 1: Single Agent + MCP Toolset

Use when:
- One bounded problem domain.
- Limited tool count and straightforward routing.

Key controls:
- Tool allowlist.
- Strict timeout/retry limits.
- Output schema validation.

## Pattern 2: Manager Agent + Specialist Workers

Use when:
- Multiple tool domains (for example data, ticketing, deployment).
- Need policy-aware delegation and synthesis.

Key controls:
- Manager enforces tool domain boundaries.
- Worker-specific credential scoping.
- Deterministic stop conditions.

## Pattern 3: Workflow-Gated MCP Calls

Use when:
- Deterministic sequence matters.
- Approval steps are mandatory.

Key controls:
- Explicit workflow graph.
- Human approval node before mutating calls.
- Compensating step definitions for rollback.

## Selection Heuristic

1. Start with single-agent + allowlisted tools.
2. Add manager/worker only for real domain decomposition.
3. Move to workflow-gated pattern for regulated or high-impact operations.
