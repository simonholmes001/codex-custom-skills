# Legacy Code And Characterization

## Goal

Introduce safety before behavior change.
Capture current observable behavior with characterization tests.

## Entry Strategy

- Identify stable seam around the change area.
- Add broad integration characterization test if internals are opaque.
- Shrink scope toward unit tests as seams improve.

## Characterization Test Rules

- Assert what system currently does, even if imperfect.
- Label surprising behavior explicitly in test names.
- Avoid asserting accidental side effects unless required.
- Add regression tests for known defects before fixing them.

## Seam Creation Techniques

- Wrap external API calls in adapter interfaces.
- Extract pure logic from side-effecting methods.
- Introduce dependency injection for hardcoded globals.
- Use feature flags for staged behavior replacement.

## Strangler Approach

For large rewrites:

1. Add contract tests around existing behavior.
2. Build new implementation behind the same contract.
3. Route small traffic slices or code paths to new implementation.
4. Remove old path when confidence is high.

## Risk Controls

- Keep changes small and reversible.
- Prefer additive refactors before deletions.
- Track metrics and logs for changed paths.
- Preserve observability during transition.
