# Azure Architecture Review Checklist

Use this checklist to evaluate proposed architecture quality before implementation.

## Reliability

- Recovery objectives (RTO/RPO) are explicitly defined.
- Failure domains (zone/region) are identified and mitigated.
- State, backup, and restore processes are tested.
- Critical dependencies have redundancy or failover paths.

## Security

- Identity model follows least privilege and separation of duties.
- Data protection includes encryption in transit and at rest.
- Public exposure is minimized and justified.
- Security monitoring and alerting are configured and owned.

## Cost Optimization

- Sizing assumptions and autoscale boundaries are documented.
- Non-production cost controls (schedules, SKUs, lifecycle) are defined.
- High-cost architectural choices are justified by business need.
- FinOps ownership and budget thresholds are assigned.

## Performance Efficiency

- Workload latency and throughput targets are documented.
- Regional placement aligns with user and dependency latency.
- Caching, data partitioning, and scaling strategies are explicit.
- Performance test approach exists for peak scenarios.

## Operational Excellence

- Infrastructure and policy are codified with version control.
- Deployment process includes approvals and rollback method.
- Observability baseline covers logs, metrics, traces, and alerts.
- Incident ownership and escalation paths are clear.

## Governance and Compliance

- Management group and subscription alignment is intentional.
- Required policies are assigned and compliance reporting is available.
- Data residency and retention controls are enforced.
- Exceptions are tracked with expiry and accountable owners.

## Architecture Quality Gate

Approve architecture only when:
1. All critical checklist items are satisfied.
2. Outstanding risks have owners and dates.
3. Rollout sequence and rollback plan are documented.
