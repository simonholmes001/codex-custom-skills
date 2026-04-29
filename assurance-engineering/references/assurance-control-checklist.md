# Assurance Control Checklist (Azure + AI)

Use this checklist to run a fast assurance pass. Mark each control as:
- `Pass` (effective with evidence)
- `Partial` (implemented but weak or unproven)
- `Fail` (missing or ineffective)
- `Unknown` (insufficient evidence)

## A. Security Baseline Controls

1. Identity and access control
- Verify least-privilege RBAC and privileged access controls.
- Verify managed identity usage over embedded credentials.
- Evidence: role assignments, PIM/JIT logs, identity architecture docs.

2. Secrets and key management
- Verify secrets are stored in managed secret stores and rotated.
- Verify key usage boundaries and access policies.
- Evidence: key vault policies, rotation schedules, secret scanning results.

3. Network security
- Verify segmentation, restricted ingress/egress, and private access patterns.
- Verify exposure minimization for management and data endpoints.
- Evidence: NSG/Firewall rules, private endpoint configs, topology diagrams.

4. Data protection
- Verify encryption in transit and at rest.
- Verify data classification and handling requirements.
- Evidence: encryption settings, data flow maps, policy controls.

5. Operational security
- Verify logging, alerting, incident response, and vulnerability management.
- Evidence: SIEM alerts, incident runbooks, remediation SLA tracking.

## B. Operational Excellence Controls

1. DevOps operating model
- Verify shared ownership, clear accountability, and routine retrospectives.
- Evidence: team operating model, post-incident review artifacts.

2. Development and change standards
- Verify standard SDLC, code review gates, branching/release strategy.
- Evidence: pipeline policies, PR checks, change management records.

3. Observability quality
- Verify actionable telemetry coverage across infra/app/deployment.
- Verify alert quality (low noise, clear owners, response playbooks).
- Evidence: dashboards, SLOs, alert definitions, on-call metrics.

4. Automation depth
- Verify repetitive high-risk tasks are automated.
- Verify automation components are treated as critical dependencies.
- Evidence: automation inventory, job success rates, failure recovery docs.

5. Safe deployment practices
- Verify IaC-first deployments and progressive rollout strategy.
- Verify rollback/mitigation procedures are tested.
- Evidence: deployment templates, staged rollout logs, rollback test results.

## C. AI Security Assurance Controls

1. Prompt injection defense
- Verify controls for both direct and indirect prompt injection.
- Verify treatment of untrusted external content paths.
- Evidence: Prompt Shields configuration, gateway/policy rules, test cases.

2. Safety filtering and harm prevention
- Verify content filtering for harmful outputs and policy violations.
- Verify risk thresholds and blocked-response behavior.
- Evidence: content safety settings, moderation logs, exception approvals.

3. Grounding and output reliability
- Verify controls for ungrounded responses and sensitive data exfiltration.
- Evidence: grounding strategy docs, evaluation reports, red-team findings.

4. Runtime detection and response
- Verify AI-specific security alerts are integrated with SecOps workflows.
- Evidence: Defender/alert integrations, triage playbooks, response metrics.

5. Assurance testing cadence
- Verify regular adversarial testing and control revalidation.
- Evidence: test schedule, drift findings, remediation closure records.

## D. Reporting Template

For each failed or partial control, report:
1. Risk statement
2. Business/technical impact
3. Missing or weak evidence
4. Recommended remediation
5. Owner and target date
6. Residual risk after remediation
