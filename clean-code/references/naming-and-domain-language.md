# Naming And Domain Language

## Naming Rules

- Name by intent, not implementation detail.
- Use business/domain language consistently.
- Prefer specific nouns and active verbs.
- Avoid ambiguous abbreviations.
- Avoid encoding mutable assumptions into names.

## Variable Naming

- Use short names only for narrow local scopes.
- Prefer singular/plural accuracy.
- Name booleans as predicates (`is`, `has`, `can`, `should`).
- Avoid names like `data`, `info`, `obj`, `tmp` unless truly generic.

## Function Naming

- Start with clear action verb.
- Express side effects in the name when relevant.
- Separate query names from command names.

## Type And Module Naming

- Reflect role and boundary.
- Avoid generic suffixes (`Manager`, `Helper`, `Utils`) unless domain-justified.
- Group by business capability, not technical convenience.

## Consistency Discipline

- Choose one term per concept and enforce it.
- Replace synonyms that fragment understanding.
- Align names across code, tests, docs, and API contracts.
