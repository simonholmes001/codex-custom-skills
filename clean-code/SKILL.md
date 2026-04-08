---
name: clean-code
description: Comprehensive clean code guidance for writing, reviewing, and refactoring maintainable software across languages and codebases. Use when Codex needs to improve readability, naming, function/class design, module boundaries, error handling, state management, testing quality, API ergonomics, code review rigor, technical debt control, and long-term maintainability without changing intended behavior.
---

# Clean Code

## Overview

Use this skill to produce code that is easy to read, easy to change, and hard to misuse.
Optimize for maintainability and correctness over cleverness.

## Quick Start Workflow

1. Clarify behavior and constraints before touching code.
2. Identify the smallest safe change that improves clarity or correctness.
3. Apply clean code rules for naming, structure, and boundaries.
4. Preserve behavior with focused tests.
5. Refactor in small, reversible steps.
6. Re-run quality gates and summarize tradeoffs.

## Load References By Need

- Read `references/clean-code-foundations.md` for first-principles and core standards.
- Read `references/naming-and-domain-language.md` for naming strategy and terminology consistency.
- Read `references/functions-and-methods.md` for function shape, arguments, and side effects.
- Read `references/classes-modules-and-packages.md` for cohesion, coupling, and boundaries.
- Read `references/state-and-side-effects.md` for mutability control and determinism.
- Read `references/error-handling-and-reliability.md` for robust failure handling and observability.
- Read `references/api-and-interface-design.md` for stable, easy-to-use interfaces.
- Read `references/comments-documentation-and-communication.md` for comments and docs policy.
- Read `references/testing-and-testability.md` for testable design and maintainable test suites.
- Read `references/refactoring-playbook.md` for safe, incremental refactoring execution.
- Read `references/code-review-checklist.md` for review standards and defect detection.
- Read `references/security-performance-and-scalability.md` for non-functional concerns.
- Read `references/legacy-modernization-and-technical-debt.md` for large-scale cleanup strategy.
- Read `references/language-specific-notes.md` for language-aware clean-code adjustments.
- Read `references/clean-code-anti-patterns.md` to detect common failures quickly.

## Default Execution Rules

- Prefer explicitness over implicit behavior.
- Keep responsibilities narrow and names precise.
- Minimize hidden side effects and shared mutable state.
- Isolate infrastructure from domain logic.
- Write code for future readers with no prior context.
- Reject unnecessary abstraction and speculative generalization.
- Preserve behavior during refactors unless requirements explicitly change.
- Keep diffs focused: one coherent intent per change.

## Definition Of Done (Clean Code)

- Code reads linearly without requiring deep mental simulation.
- Naming reflects domain intent and constraints.
- Functions and modules have focused responsibilities.
- Error paths are explicit and actionable.
- Tests cover behavior and remain understandable.
- Comments explain why, not what code already states.
- New complexity is justified and documented.

## Response Template During Task Execution

Use this structure when reporting clean-code work:

1. `Intent`: what was improved and why.
2. `Change`: structural and naming updates made.
3. `Safety`: tests and checks run to confirm behavior preservation.
4. `Tradeoffs`: acceptable compromises or deferred follow-ups.
5. `Next`: optional targeted improvements.
