# Legacy Migration Playbook

## Starting Point

- Map current hotspots: change frequency, incident density, coupling.
- Identify seams around high-value use cases.
- Add characterization tests before structural changes.

## Incremental Migration Steps

1. Define target boundaries and dependency direction.
2. Introduce ports around volatile infrastructure.
3. Move policy logic into use cases and entities.
4. Add adapters for old and new paths in parallel.
5. Cut over by capability with monitoring.
6. Remove obsolete paths and simplify.

## Risk Controls

- Keep each migration slice small and reversible.
- Use feature flags for traffic control.
- Maintain parity checks during dual-run periods.
- Track migration debt and close it explicitly.

## Completion Criteria

- Critical capabilities run through new architecture paths.
- Legacy entry points are either retired or isolated.
- Dependency rule enforcement is automated in CI.
