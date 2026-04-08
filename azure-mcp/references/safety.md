# Azure MCP Safety

## Approval Boundaries

Require explicit user approval before:
- Network/security mutations (NSG, routing, firewall, private endpoint)
- IAM/RBAC changes
- Production resource deletions
- Policy assignment or exemption changes

## Write Guardrails

- Confirm tenant/subscription/resource scope before mutation.
- Prefer read-only diagnostics first.
- Apply smallest viable change and avoid multi-resource blast radius.
- Define rollback and validation before change execution.

## Operational Guardrails

- Surface privilege limits and missing permissions early.
- Escalate ambiguity in environment or target resource names.
- Report exact resource IDs and before/after state for every write.
