# Twelve-Factor Checklist

Use this rubric for factor-by-factor assessment and remediation planning.

## Scoring

- `meets`: implemented and evidenced in code/config/runtime
- `partial`: some implementation exists, but with notable gaps
- `gap`: missing or materially non-compliant

## 1) Codebase

- One codebase tracked in version control.
- Multiple deploys from the same codebase are environment variants, not forks.
- Gap signals: manual hotfixes on servers, environment-specific branches as primary strategy.

## 2) Dependencies

- Declare dependencies explicitly in manifests.
- Isolate dependencies from the host runtime.
- Gap signals: implicit global packages, undeclared transitive reliance, mutable base images.

## 3) Config

- Store environment-varying config in environment variables or secure runtime configuration.
- Keep secrets out of source control and static appsettings committed for all environments.
- Gap signals: secrets in repo, hardcoded endpoints/keys, per-environment code branches.

## 4) Backing Services

- Treat databases, queues, caches, and external services as attached resources.
- Swap attached resources via config without code changes.
- Gap signals: service endpoints hardcoded in code, compile-time environment coupling.

## 5) Build, Release, Run

- Separate build artifact creation from release promotion and runtime execution.
- Make releases immutable and identifiable.
- Gap signals: building directly in production, ad-hoc runtime mutations.

## 6) Processes

- Execute app as one or more stateless processes.
- Persist state in backing services, not process memory or local writable filesystem assumptions.
- Gap signals: sticky in-memory sessions, single-instance local state requirements.

## 7) Port Binding

- Export services via port binding and self-contained runtime.
- Gap signals: relying on in-process web server assumptions or external web container coupling.

## 8) Concurrency

- Scale out via process model (web/worker/etc.).
- Distinguish process types and scale independently.
- Gap signals: monolithic process with no role separation, scale-up only path.

## 9) Disposability

- Fast startup and graceful shutdown.
- Support safe restarts, rolling deploys, and crash recovery.
- Gap signals: long blocking startup, missing signal handling, unsafe termination behavior.

## 10) Dev/Prod Parity

- Keep development, staging, and production as similar as practical.
- Minimize time and tooling drift between environments.
- Gap signals: local-only dependencies, non-reproducible setup, major runtime mismatch.

## 11) Logs

- Treat logs as event streams written to stdout/stderr and aggregated externally.
- Gap signals: app-managed log files as primary sink, local disk log dependence.

## 12) Admin Processes

- Run one-off admin tasks as ephemeral processes against the same code/config as long-running processes.
- Gap signals: manual server shell scripts with drifted dependencies or config.

## Prioritization Heuristics

- High: secrets/config flaws, stateful process model, poor disposability.
- Medium: build-release-run coupling, parity gaps causing delivery failures.
- Lower: maturity optimizations where risk is contained.

## Output Template

For each factor:

`Factor N - Name`
- Status:
- Evidence:
- Risk:
- Remediation:
- Effort:
