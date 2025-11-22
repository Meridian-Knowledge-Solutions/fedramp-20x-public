# KSI-AFR-10: Integrate FedRAMP's Incident Communications Procedures (ICP) into incident response procedures and persistently address all related requirements and recommendations.

## Overview

**Category:** Other
**Status:** FAIL
**Last Check:** 2025-11-22 01:14

**What it validates:** Integrate FedRAMP's Incident Communications Procedures (ICP) into incident response procedures and persistently address all related requirements and recommendations.

**Why it matters:** Validates ICP Playbook AND Incident Response Plan documents exist, PLUS validates existing incident logging workflow (incident_logging.yaml) and supporting notification infrastructure (SNS topics with confirmed subscriptions).

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path procedures/icp_playbook.md --output json`
   *Governance: Validates ICP Playbook documentation exists with FedRAMP notification procedures.*

2. `aws codecommit get-file --repository-name security-governance --file-path procedures/incident-response-plan.md --output json`
   *Governance: Validates Incident Response Plan documentation exists with NIST IR phases.*

3. `aws codecommit get-file --repository-name fedramp-20x-submission-final --file-path .github/workflows/incident_logging.yaml --output json`
   *Automation: Validates existing incident logging workflow is configured (weekly analysis + historical tracking).*

4. `aws sns list-topics --output json`
   *Alerting: Validates SNS topics exist for incident notifications (incident-alert-processor, incident-notifications).*

5. `aws sns list-subscriptions --output json`
   *Alerting: Validates SNS subscriptions are configured and confirmed for incident notifications (fedramp-security@, security@).*

## Latest Results

FAIL Insufficient 0/10 (0%): FAIL [ICP Playbook] ICP playbook not found in security-governance repo
- FAIL [Incident Response Plan] Incident response plan not found in security-governance repo
- FAIL [Automation] incident_logging.yaml workflow not found in repository
- WARNING [SNS Topics] Could not verify SNS topic configuration
- WARNING [SNS Subscriptions] Could not verify SNS subscriptions

---
*Generated 2025-11-22 01:27 UTC*