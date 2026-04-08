# Azure Networking Troubleshooting Playbooks

## Symptom: VM cannot reach private endpoint

1. Confirm source DNS resolves FQDN to private endpoint IP.
2. Confirm private DNS zone is linked to source VNet.
3. Confirm source subnet NSG egress allows target port.
4. Confirm target subnet/endpoint policy allows source path.
5. Confirm effective route sends traffic to expected next hop.

## Symptom: Spoke-to-spoke traffic fails in hub-and-spoke

1. Confirm peering state is Connected in both directions.
2. Confirm `allowForwardedTraffic` and gateway transit flags are correct.
3. Confirm UDRs in spokes direct traffic to hub firewall/NVA.
4. Confirm firewall/NVA rules allow both directions.
5. Confirm return path symmetry to avoid stateful drop.

## Symptom: Internet egress intermittently fails

1. Check SNAT utilization on NAT Gateway or firewall.
2. Confirm no conflicting default routes (0.0.0.0/0).
3. Confirm upstream dependency and destination rate limits.
4. Validate DNS response latency and retry behavior.
5. Inspect NSG flow logs and firewall logs for deny patterns.

## Symptom: On-prem to Azure over VPN unstable

1. Confirm VPN tunnel status and negotiated parameters.
2. Confirm BGP sessions and learned routes on both sides.
3. Confirm no overlapping prefixes with VNet/spoke ranges.
4. Confirm MTU/MSS assumptions for application protocol.
5. Check if asymmetric routing appears after failover.

## Symptom: Name resolution works in Azure but fails on-prem

1. Confirm conditional forwarder exists for private zone domain.
2. Confirm DNS forward path to Azure resolver/forwarder.
3. Confirm return recursion path and firewall UDP/TCP 53.
4. Confirm private zone records exist and are not stale.
5. Confirm clients do not bypass intended recursive resolver.

## Evidence-first troubleshooting order

1. Reproduce exact flow tuple: source, destination, port, protocol.
2. Validate DNS answer seen by source.
3. Validate effective NSG.
4. Validate effective route.
5. Validate intermediary device policy and health.
6. Validate target-side access control.
