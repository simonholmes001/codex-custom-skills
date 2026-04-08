# Clean Code Foundations

## Primary Goal

Maximize long-term maintainability while preserving correctness.
Treat readability as a functional requirement.

## Core Principles

- Prefer clear intent over clever implementation.
- Minimize cognitive load per function and per module.
- Keep behavior predictable and explicit.
- Make illegal states hard to represent.
- Optimize for safe change over short-term convenience.

## Practical Standards

- Keep units small but meaningful.
- Encode domain concepts in types and interfaces.
- Keep dependency direction intentional.
- Avoid hidden control flow and hidden state.
- Ensure failure modes are explicit and observable.

## Clarity Heuristics

Code is likely clean when a reviewer can answer quickly:

- What does this do?
- Why does it exist?
- What assumptions does it rely on?
- What can fail and how is it handled?
- Where should a related change be made?

## Cost Awareness

Prefer solutions that reduce future change cost:

- Lower onboarding effort.
- Lower defect injection risk.
- Lower regression risk during refactors.
- Lower effort to isolate and fix production incidents.
