# Cross-Skill Standards

These standards apply to all custom skills.

## 1) Evidence Quality Rubric

Classify every major conclusion:

- `Verified`: directly supported by canonical source content and concrete artifacts.
- `Derived`: inferred from multiple verified signals.
- `Assumption`: not directly supported; requires validation.

Never present assumptions as verified facts.

## 2) Context Budget and Loading Policy

Use progressive disclosure to control context size:

1. Load only `SKILL.md` + source index first.
2. Load only the reference sections required by current scope.
3. Prefer scoped passes over full passes when the request is narrow.
4. If context pressure exists, prioritize: source index -> protocol -> domain references -> examples.

Always state what was intentionally not loaded.

## 3) Anti-Patterns and Handoff Rules

Avoid:

- Broad recommendations without explicit source coverage.
- Control claims without evidence artifacts.
- Overfitting to a preferred technology before requirements are explicit.
- Mixing verified facts with assumptions without labels.

Handoff to a different skill when problem scope primarily belongs to another domain.

## 4) Source Freshness Policy

For high-stakes guidance (security, legal, financial, production operations):

1. Re-check canonical sources for freshness before final recommendations.
2. Record source currency/date when available.
3. Flag stale or ambiguous references and reduce confidence accordingly.

## 5) Minimum Output Additions

Non-trivial responses must include:

1. `Source Coverage Summary`
2. `Evidence Quality Notes`
3. `Assumptions and Residual Risks`
