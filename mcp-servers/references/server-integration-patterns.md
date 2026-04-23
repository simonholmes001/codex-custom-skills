# Server Integration Patterns

## Pattern 1: Single Local MCP Server

Use when:
- One bounded domain/toolset.
- Fast local iteration and low deployment complexity.

Tradeoffs:
- Simple setup and debug.
- Limited organizational reuse at scale.

## Pattern 2: Multi-Server Aggregation

Use when:
- Capabilities are separated by domain (code, tickets, cloud ops, data).
- Different security boundaries are required.

Tradeoffs:
- Better separation and governance.
- Higher routing and lifecycle complexity.

## Pattern 3: Remote Managed MCP Server

Use when:
- Shared enterprise access and central policy is required.
- Multiple clients consume the same controlled capability set.

Tradeoffs:
- Better control plane and reuse.
- Additional network/auth/dependency considerations.

## Selection Heuristic

1. Start with a single server for one domain.
2. Split servers when policy/ownership boundaries diverge.
3. Move to managed remote model when reuse/governance outweigh local simplicity.
