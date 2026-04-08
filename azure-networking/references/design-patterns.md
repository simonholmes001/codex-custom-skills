# Azure Networking Design Patterns

## Pattern 1: Single VNet, Tiered Subnets

Use for small to medium workloads in one region.

- Create dedicated subnets per tier (web, app, data, management).
- Attach NSGs at subnet level first; use NIC NSGs only for exceptions.
- Keep UDR usage minimal to reduce asymmetric route risk.
- Use NAT Gateway for private outbound at scale.

## Pattern 2: Hub-and-Spoke

Use for multi-workload environments with shared services.

- Place shared controls in hub: Firewall, DNS forwarders, Bastion, VPN/ER.
- Peer spokes to hub with gateway transit as needed.
- Enforce spoke-to-spoke policy via hub inspection path.
- Keep address spaces non-overlapping across spokes.

## Pattern 3: Virtual WAN

Use for many branches/regions requiring managed transit.

- Prefer for large branch connectivity and global transit simplification.
- Centralize policy and routing intent in VWAN hub.
- Validate SKU and routing intent limitations before adoption.

## Private PaaS Access

- Prefer Private Endpoint for data exfiltration control and private IP path.
- Use Private DNS zones and zone links to every participating VNet.
- Validate split-horizon DNS behavior for hybrid resolvers.
- Use Service Endpoints only when Private Endpoint is unnecessary.

## Security Control Placement

- Use NSGs for L3/L4 segmentation closest to workload.
- Use Azure Firewall/NVA for centralized policy, threat intel, and logging.
- Use ASGs to avoid large NSG IP rule sets where possible.
- Avoid duplicate controls without explicit ownership boundaries.

## Routing Principles

- Keep route domains simple; document source of truth per subnet.
- Confirm longest-prefix match outcomes before adding UDRs.
- Prevent accidental Internet default routes from overriding private paths.
- Validate forced tunneling impacts on PaaS dependencies.

## DNS Principles

- Define one resolver authority chain per environment.
- Use Azure Private DNS Resolver for hybrid conditional forwarding patterns.
- Keep private zone naming consistent with service standards.
- Test both A and CNAME answers from workload perspective.
