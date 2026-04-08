# Azure Architecture Decision Patterns

## Topology Pattern Selection

Choose based on scale and control requirements:

- Single VNet pattern:
  - Use for small solutions with limited shared services.
  - Keep operations simple and low overhead.
- Hub-and-spoke pattern:
  - Use for multi-workload environments with shared controls.
  - Centralize connectivity, DNS, and security services.
- Virtual WAN pattern:
  - Use for large branch/global transit requirements.
  - Prefer when managed transit and simplified branch connectivity are priorities.

## Compute Pattern Selection

- App Service / Functions:
  - Use for managed PaaS with reduced ops burden.
  - Prefer when runtime constraints fit platform limits.
- AKS:
  - Use for container orchestration and portability requirements.
  - Require clear platform ownership and SRE maturity.
- Virtual Machines:
  - Use for legacy dependencies or deep OS control requirements.
  - Plan patching and hardening ownership explicitly.

## Data Pattern Selection

- Azure SQL Database:
  - Use for relational workloads with managed operations.
- Cosmos DB:
  - Use for globally distributed low-latency access patterns.
- Storage + analytics services:
  - Use for data lake and batch/stream analytical pipelines.

## Connectivity Pattern Selection

- Site-to-Site VPN:
  - Use for quick hybrid onboarding and lower throughput needs.
- ExpressRoute:
  - Use for private, predictable connectivity and strict compliance.

## Security Control Pattern Selection

- NSG-first segmentation:
  - Use for basic L3/L4 isolation near workloads.
- Central firewall/NVA inspection:
  - Use when centralized policy and traffic inspection are required.
- Private endpoint first:
  - Use for sensitive service access and data exfiltration risk reduction.

## Decision Recording Template

For each major decision, capture:
1. Context and requirement
2. Options considered
3. Selected option and rationale
4. Tradeoffs and accepted risks
5. Validation criteria
