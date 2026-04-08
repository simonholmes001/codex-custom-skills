# Azure Landing Zone Blueprint

## Objective

Establish a secure, governable, and scalable Azure foundation before workload onboarding.

## Core Platform Areas

1. Identity and Access
- Centralize identity in Microsoft Entra ID.
- Enforce MFA and Conditional Access for privileged access.
- Use least-privilege RBAC with role assignment at management group/subscription scope.
- Prefer managed identities over secrets for workload auth.

2. Resource Organization
- Define management group hierarchy by business boundary and environment model.
- Separate platform, sandbox, and production workloads into distinct subscriptions.
- Standardize naming and tagging for ownership, cost, data classification, and environment.

3. Networking
- Choose hub-and-spoke or Virtual WAN for shared services at enterprise scale.
- Reserve CIDR ranges up front to avoid overlap with on-prem and future regions.
- Centralize outbound control and inspection where required.
- Use private connectivity patterns for sensitive PaaS dependencies.

4. Governance
- Deploy Azure Policy initiatives for mandatory guardrails.
- Enforce allowed regions, approved SKUs, encryption, diagnostic settings, and tagging.
- Define an exemption workflow with owner, reason, and expiration date.

5. Security
- Enable Defender plans aligned to workload types.
- Standardize vulnerability management and baseline hardening.
- Route key security signals to SIEM/SOC workflows.

6. Operations
- Standardize monitoring, logging, alerting, and dashboard baselines.
- Define backup and recovery patterns by workload tier.
- Set up change management and incident response runbooks.

## Environment Model

- Use isolated subscriptions per environment for production-grade workloads.
- Keep shared platform services in dedicated subscriptions.
- Avoid mixing unrelated production workloads without explicit governance approval.

## Onboarding Sequence

1. Establish identity, policy, and baseline monitoring.
2. Deploy network foundation and shared services.
3. Create subscription vending and role assignment process.
4. Validate guardrails with pilot workload.
5. Scale onboarding using documented patterns.
