# .NET API Surface Notes (`Microsoft.Agents.AI`)

Use this guide for API discovery and implementation orientation against the latest .NET namespace docs.

## Namespace-first Navigation

- Start with the namespace page to identify core abstractions before reading samples.
- Build an internal map of:
1. Agent abstractions and run APIs.
2. Message/content models.
3. Tool definitions and invocation types.
4. Middleware/context/session primitives.

## Implementation Practice

- Prefer strongly typed request/response handling over ad-hoc dynamic parsing.
- Keep provider-specific APIs behind adapter classes; use common `AIAgent` patterns in application code.
- Pin prerelease package versions deliberately and validate compatibility in CI.

## Upgrade Discipline

- Review API docs per upgrade for signature/behavior changes.
- Run smoke tests for:
1. `RunAsync` and streaming behavior.
2. Tool invocation and approval paths.
3. Session persistence and restore.

## Documentation Hygiene

- When answering users, cite namespace/API docs for class-level specifics rather than inferring signatures.
