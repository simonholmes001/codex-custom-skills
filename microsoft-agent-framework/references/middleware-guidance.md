# Middleware Guidance (C#-oriented)

Use this guide when implementing cross-cutting controls around agent and chat execution.

Evidence level: `Derived` (aligned to official middleware topics; implementation shape may vary across prerelease packages).

## Middleware Responsibilities

- Put cross-cutting concerns in middleware:
1. Policy checks and redaction.
2. Logging and telemetry enrichment.
3. Retry/timeouts and circuit breakers.
4. Validation and normalization.
- Keep business logic in tools/services, not middleware.

## Defining Middleware

- Implement small, single-purpose middleware components and chain them intentionally.
- Ensure middleware is side-effect aware; idempotency matters when retries occur.
- Normalize errors to predictable shapes so orchestration can handle failures deterministically.

```csharp
// Pattern sketch: wrap next() with policy, telemetry, and termination guards.
public sealed class GuardMiddleware
{
    public async Task InvokeAsync(RunContext ctx, Func<Task> next)
    {
        using var _ = ctx.Telemetry.Start("guard_middleware");
        if (ctx.Iteration > 20) throw new InvalidOperationException("Max iterations exceeded.");
        await next();
    }
}
```

## Chat Middleware

- Use chat middleware when concern is provider-call scoped (pre/post model invocation).
- Use agent middleware when concern spans planning, tool routing, and run lifecycle.
- Avoid duplicate policy enforcement across both layers unless required by compliance.

## Agent Scope vs Run Scope

- Agent-scope middleware:
1. Reusable defaults for every run of an agent.
2. Stable, environment-level policy.
- Run-scope middleware:
1. Per-request policy/customization.
2. Tenant/user/request-specific controls.
- Prefer run-scope for request-specific behavior to avoid hidden global coupling.

## Termination Controls

- Add explicit termination middleware for loop-prone orchestration.
- Enforce max-iteration, max-tool-calls, elapsed-time, and stall-detection thresholds.
- Surface termination reasons to logs and caller responses.

## Operational Guidance

- Instrument each middleware stage with timing and outcome tags.
- Capture policy decisions and override reasons for audits.
- Test middleware ordering, because order can materially change behavior.
