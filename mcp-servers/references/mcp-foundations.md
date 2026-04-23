# MCP Foundations Notes

## What MCP Provides

Model Context Protocol (MCP) is an open standard for connecting AI applications to external tools, data sources, and workflows via a consistent interface.

Think of MCP as a standardized integration port between AI clients and external capabilities.

## Core Roles

- MCP Client: the AI application or agent runtime that connects to servers.
- MCP Server: exposes tools/resources/prompts/capabilities.
- Transport/session layer: carries requests and responses between client and server.

## Why It Matters

- Standardizes integration across heterogeneous tools.
- Reduces bespoke adapter code per AI client.
- Enables reusable server ecosystems and consistent governance.

## Practical Implications

- Capability discovery should be explicit and policy-filtered.
- Tool invocation paths need clear auth and timeout boundaries.
- Output contracts should be validated before downstream use.
