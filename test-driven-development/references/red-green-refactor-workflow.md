# Red Green Refactor Workflow

## Session Setup

- Restate acceptance criteria in executable terms.
- Identify the first user-visible behavior slice.
- Pick the smallest test level that can validate that slice.
- Start with one concrete example before generalized behavior.

## Red Phase

- Write one test expected to fail for a known reason.
- Run only that test to confirm real failure.
- Ensure failure is about missing behavior, not setup mistakes.
- Avoid writing multiple new failing tests at once unless tightly coupled.

## Green Phase

- Implement the minimum code to satisfy the failing test.
- Resist preemptive abstractions.
- Run the narrow suite, then the broader impacted suite.
- Stop once green is achieved.

## Refactor Phase

- Improve naming, extraction, and duplication.
- Remove incidental complexity introduced in Green.
- Re-run tests continuously after small edits.
- Keep behavior unchanged; avoid adding new functionality here.

## Micro-Cycle Heuristics

- Target 2 to 10 minutes per loop.
- If a test takes over 15 minutes to make pass, split the behavior.
- If uncertainty is high, add a smaller stepping-stone test.
- If refactor risk feels high, create a protective test before change.

## Commit Strategy

- Prefer commits that contain one coherent behavior increment.
- Include tests and production code together.
- Keep commit messages behavior-oriented, not file-oriented.
- Avoid large mixed commits with unrelated refactors.

## Failure Recovery

- If stuck in Red, simplify assertion scope or improve test seam.
- If Green requires broad code edits, you skipped smaller tests; step back.
- If Refactor keeps breaking tests, reduce refactor step size.
- If the cycle drifts, restate the behavior in one sentence and restart.

## Completion Checklist For A Story

- All acceptance behaviors have tests.
- Regression tests cover fixed bugs.
- Broad suite for impacted area is green.
- New code is readable without test-only knowledge.
- Remaining technical debt is captured explicitly.
