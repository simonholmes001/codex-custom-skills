# Azure MCP Server Notes

## Scope

Azure MCP Server enables MCP-compatible clients and agents to access Azure capabilities through MCP tools.

## Typical Use Cases

- Natural-language-assisted cloud operations.
- AI agents invoking Azure management and service workflows.
- Unified Azure tool access from IDE agents and MCP clients.

## Doc Areas to Use

From the Azure docs landing page:
- Overview and authentication guidance.
- Installation in IDEs/package managers.
- Connections from tooling and coding agents.
- Sovereign cloud and remote deployment guidance.
- Tool reference and complete tool list.

## Integration Guidance

- Confirm tenant/subscription/resource scope early.
- Apply least privilege to identities calling Azure tools.
- Keep production writes approval-gated.
- Capture call traceability for audit and troubleshooting.
