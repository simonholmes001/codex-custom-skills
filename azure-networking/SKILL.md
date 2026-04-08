---
name: azure-networking
description: Design, review, and troubleshoot Microsoft Azure networking architectures and connectivity. Use when Codex needs to plan or diagnose virtual networks, subnets, NSGs, route tables, VNet peering, VPN Gateway, ExpressRoute, Private Endpoints, Azure Firewall, NAT Gateway, DNS/Private DNS, network segmentation, or hub-and-spoke landing zone connectivity.
---

# Azure Networking

## Overview

Design secure, operable Azure network topologies and resolve packet path issues with deterministic checks. Keep architecture decisions explicit and verify control plane and data plane behavior separately.

## Workflow

1. Collect scope, region, and connectivity requirements before proposing changes.
2. Choose target topology and controls by using `references/design-patterns.md`.
3. Validate effective routes, effective NSGs, DNS resolution, and next hop state in that order.
4. Propose smallest safe change, define rollback, then stage rollout by blast radius.

## Official Documentation

Use `references/official-docs.md` when authoritative or current platform guidance is needed.
- Prefer these links for best-practice and design recommendations.
- Cite the exact page used when answering architecture or troubleshooting questions.

## Gather Inputs

Collect these values first:
- Subscription and tenant boundary
- Regions, availability zones, and latency/SLA targets
- Address plan (CIDRs), overlap risks, and future growth
- North-south paths (Internet, on-prem, partners)
- East-west paths (app tiers, shared services, data stores)
- Security policy intent (deny-by-default, inspection points, egress control)
- Name resolution model (Azure DNS, custom DNS, Private DNS zones)
- Required private service access (Private Endpoint/Service Endpoint)

## Select Topology

Apply this decision order:
1. Choose segmentation model: flat VNet, tiered subnets, or hub-and-spoke.
2. Choose transitive connectivity: Virtual WAN vs hub VNet with NVA/Azure Firewall.
3. Choose hybrid edge: Site-to-Site VPN first, then ExpressRoute for deterministic private throughput/compliance.
4. Choose private PaaS model: Private Endpoint by default; use Service Endpoints only when simpler and acceptable.
5. Choose outbound model: NAT Gateway for scale SNAT, Azure Firewall for policy + logging.

Use `references/design-patterns.md` for pattern-specific tradeoffs.

## Troubleshoot Connectivity

Run checks in this sequence to avoid false leads:
1. Confirm intended source and destination IP/FQDN and transport (TCP/UDP/ICMP).
2. Confirm NIC/subnet effective NSG allows the flow both directions.
3. Confirm effective route table next hop and prefix match behavior.
4. Confirm DNS answer at source workload and resolver chain behavior.
5. Confirm intermediary controls (Firewall/NVA/LB) and health probes.
6. Confirm target service policy (Private Endpoint ACL, app firewall, host firewall).

Use `references/troubleshooting-playbooks.md` for symptom-driven checks and command sequence.

## Change Safety

Always produce:
- Assumptions list
- Exact impacted resources
- Validation checks before and after change
- Rollback command/setting
- Expected telemetry signals (Network Watcher, NSG flow logs, Firewall logs)

Prefer low-risk staged rollout:
1. Apply to test subnet or one spoke.
2. Validate packet path and app health.
3. Expand gradually.

## Commands

Use `references/cli-recipes.md` for copy/paste `az` commands:
- Effective route and NSG inspection
- NSG rule audits
- VNet peering state checks
- Private Endpoint and DNS zone link checks
- VPN/BGP status checks

## Output Contract

When responding with this skill:
1. State proposed architecture or diagnosis in 3-6 bullets.
2. State why that conclusion fits observed evidence.
3. Provide ordered commands or portal actions.
4. Provide validation and rollback steps.
5. Call out unresolved assumptions explicitly.
