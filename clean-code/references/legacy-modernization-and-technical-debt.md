# Legacy Modernization And Technical Debt

## Debt Classification

Classify debt before action:

- Structural debt (coupling, architecture).
- Quality debt (missing tests, flaky behavior).
- Operational debt (observability, deployment risk).
- Domain debt (misleading concepts and naming drift).

## Prioritization

Prioritize debt reduction by:

- Incident frequency and severity.
- Change frequency of affected code.
- Risk of regression.
- Team productivity impact.

## Modernization Strategy

- Add characterization tests around risky behavior.
- Create seams before deep rewrites.
- Replace subsystem boundaries incrementally.
- Remove dead code aggressively when safe.

## Governance

- Track debt items with owner and expected payoff.
- Attach cleanup tasks to feature delivery when adjacent.
- Review debt trend regularly, not only during incidents.
