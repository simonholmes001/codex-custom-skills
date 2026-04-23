# Deployment Approaches

Use this guide to choose an implementation path.

## Common Deployment Paths

1. Accelerator-led deployment
- Fast baseline for organizations adopting Microsoft reference ALZ patterns.
- Best when speed and standard alignment matter most.

2. IaC-first custom deployment
- Higher control and customization for enterprise constraints.
- Best when strict policy/network/compliance constraints require tailoring.

3. Hybrid phased approach
- Start from reference baseline, then layer organization-specific controls.
- Best when balancing speed with controlled customization.

## Sequencing Recommendation

1. Foundation
- Management groups, subscriptions, identity baseline, core policy.

2. Connectivity and Shared Services
- Hub/VWAN, DNS, firewall, private connectivity dependencies.

3. Governance and Security Hardening
- Monitoring, Defender/SIEM, policy refinement, exception workflow.

4. Workload Onboarding
- Non-prod first, then production with staged validation.

## Validation Gates

- Policy compliance score and exemption hygiene.
- Connectivity and DNS path validation.
- Security alert pipeline and ownership verification.
- Backup/restore and DR objective validation.
