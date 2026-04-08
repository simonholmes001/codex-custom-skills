# Azure MCP Workflows

## Resource Inventory Workflow

1. Resolve tenant, subscription, and resource group scope.
2. Enumerate target resources and key configuration attributes.
3. Summarize risks, drift signals, and missing controls.

## Diagnostics Workflow

1. Collect symptom, timeframe, and impacted resources.
2. Pull current state and relevant diagnostic signals.
3. Identify likely root-cause candidates.
4. Propose minimal remediation and validation checks.

## Controlled Change Workflow

1. State exact resource scope and intended mutation.
2. Record pre-change values.
3. Apply the scoped change.
4. Validate service health and configuration state.
5. Provide rollback instructions.
