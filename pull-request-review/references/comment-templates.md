# Review Comment Templates

## Finding Template

Severity: <Critical|High|Medium|Low>
Title: <short defect statement>
Evidence: <file:line + observed behavior>
Impact: <why this matters>
Fix: <smallest safe remediation>

## Example Finding

Severity: High
Title: Missing authorization check on attachment download endpoint
Evidence: `backend/src/Agon.Api/Controllers/SessionsController.cs:412` returns file content without validating session ownership.
Impact: Cross-tenant data exposure is possible if an attacker guesses IDs.
Fix: Enforce ownership check before fetching blob content; return 404/403 on mismatch and add integration test for unauthorized access.

## No-Findings Template

No blocking findings identified.
Residual risk: <list minor risks or "none observed">.
Testing gaps: <list gaps or "none observed">.

## Final Summary Template

- Reviewed scope: <high-level components>
- Findings: <count by severity>
- Merge recommendation: <approve | request changes>
- Required follow-ups: <issue links or explicit none>
