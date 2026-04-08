# Flaky Tests And Debugging

## Identify Flakiness Sources

- Time dependence and race conditions.
- Shared mutable state between tests.
- Network or external service instability.
- Order dependence and hidden test coupling.
- Randomized inputs without fixed seeds.

## Stabilization Checklist

- Freeze time with injectable clocks.
- Isolate filesystem and database fixtures.
- Reset global state after each test.
- Replace live network with fakes or contract fixtures.
- Remove sleeps; wait on explicit signals.

## Reproduction Tactics

- Run failing test repeatedly in a loop.
- Randomize test order to expose coupling.
- Run under CPU and I/O stress.
- Capture logs, traces, and deterministic seed values.

## CI Hardening

- Keep unit suite fast enough for frequent runs.
- Quarantine known flaky tests temporarily with owner and deadline.
- Track flaky frequency as an explicit quality metric.
- Block merges on chronic flakiness until resolved.

## Debugging Red In TDD

When a new test fails unexpectedly:

1. Confirm test setup and assertion correctness.
2. Minimize fixture to isolate behavior.
3. Add focused diagnostics near failing boundary.
4. Fix production code or test seam, then remove noisy diagnostics.
