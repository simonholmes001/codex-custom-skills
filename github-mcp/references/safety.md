# GitHub MCP Safety

## Approval Boundaries

Require explicit user approval before:
- Merging pull requests
- Closing or re-opening large issue sets
- Editing repository-wide settings
- Deleting branches or tags

## Write Guardrails

- Confirm target repository and object IDs before mutation.
- Limit write scope to the exact requested objects.
- Prefer incremental updates over bulk mutations.
- Capture before/after state in the response.

## Failure Handling

- Report permission failures directly and suggest required role/scope.
- Stop on ambiguous repo or object identifiers and ask for clarification.
