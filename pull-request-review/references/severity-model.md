# Severity Model

Use this model to classify findings consistently.

## Critical
- Immediate, high-impact security or safety risk.
- Data breach, auth bypass, secret exposure, destructive data corruption/deletion, or severe production outage risk.
- Merge policy: block merge until fixed.

## High
- Significant functional or reliability risk likely to affect users or production stability.
- Incorrect business logic on critical flows, unsafe migration patterns, major availability/performance risk.
- Merge policy: block merge unless explicitly accepted by owner with mitigation plan.

## Medium
- Meaningful quality or correctness issue with moderate impact.
- Edge-case regression, incomplete error handling, insufficient test coverage in non-critical paths.
- Merge policy: usually fix before merge; may defer with documented follow-up issue.

## Low
- Minor issue with limited impact.
- Maintainability gaps, non-critical observability improvements, small contract clarity issues.
- Merge policy: can merge with follow-up if risk is controlled.

## Informational
- Suggestion or clarification without clear defect.
- Merge policy: never block on informational comments alone.

## Evidence Standard

Require evidence for each finding:
- exact file/line reference,
- precise behavior,
- why behavior violates requirement or safety expectation,
- concrete fix direction.
