# Security Domains and Assessment Prompts

Use these prompts to turn guidance into concrete architecture and control decisions.

## 1) Identity and Access

- Are human and workload identities separated?
- Is MFA enforced for all privileged and remote access?
- Are privileged roles JIT/JEA through PIM and regularly reviewed?
- Are managed identities preferred over long-lived secrets?

## 2) Network and Exposure

- Is internet ingress minimized and explicitly controlled?
- Are private endpoints used for sensitive PaaS paths?
- Are segmentation and egress controls enforced with NSG/Firewall?
- Is DDoS protection and edge hardening mapped to risk profile?

## 3) Data and Cryptography

- Is data classified and encryption posture mapped per class?
- Are CMK/BYOK/HSM choices documented and justified?
- Is key lifecycle (rotation, revocation, backup) automated?
- Are storage and database hardening baselines enforced?

## 4) Platform and Host Integrity

- Are secure/measured boot and attestation controls applicable and enabled?
- Are supply chain integrity controls defined for images/artifacts?
- Are platform boundaries and shared-responsibility assumptions explicit?

## 5) Monitoring and Detection

- Are audit logs centralized, immutable where required, and retained by policy?
- Are detections mapped to ATT&CK-like behaviors and tested?
- Are alert ownership, triage SLAs, and escalation paths defined?

## 6) Incident and Ransomware Resilience

- Are playbooks rehearsed for containment, eradication, and recovery?
- Are backup isolation and restore tests performed on schedule?
- Is blast-radius reduction designed into network and identity layers?

## 7) AI Workload Security

- Are prompt-injection and data exfiltration controls in place?
- Are model/service endpoints isolated and access-scoped?
- Are AI safety and abuse-detection telemetry captured and reviewed?
