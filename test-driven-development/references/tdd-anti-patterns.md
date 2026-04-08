# TDD Anti-Patterns

## Test-After Masquerading As TDD

Symptom: production code is written first, tests are added later.
Correction: restore Red first; ensure each behavior begins with failing test.

## Giant Test Jumps

Symptom: broad end-state tests require large code leaps.
Correction: split into stepping-stone tests with smaller behavior increments.

## Overspecified Tests

Symptom: tests fail on harmless refactors.
Correction: assert externally visible behavior, not internal choreography.

## Assertion Starvation

Symptom: tests check only status codes or null/not-null.
Correction: assert meaningful domain outcomes and invariants.

## Mock Hell

Symptom: tests require many interaction mocks and setup noise.
Correction: improve design seams, use fakes, reduce collaborator count.

## Refactor Neglect

Symptom: green achieved but poor structure accumulates.
Correction: reserve explicit refactor time in each cycle.

## Slow Suite Drift

Symptom: feedback loop slows until TDD is abandoned.
Correction: rebalance test pyramid, optimize fixtures, parallelize CI strategically.

## Flaky Tolerance

Symptom: intermittent failures are ignored or retried blindly.
Correction: treat flakiness as defect; assign owner and fix root cause.

## No Regression For Bugs

Symptom: defect fix merged without failing reproducer test.
Correction: add regression test first, then implement fix.
