# KSI-AFR-10: Integrate FedRAMP's Incident Communications Procedures (ICP) into incident response procedures and infrastructure.

## Overview

**Category:** Other
**Status:** PASS
**Last Check:** 2025-11-24 18:23

**What it validates:** Integrate FedRAMP's Incident Communications Procedures (ICP) into incident response procedures and infrastructure.

**Why it matters:** Validates ICP Playbook AND Incident Response Plan documents exist (Governance), PLUS validates supporting notification infrastructure (SNS topics and subscriptions) is active (Technical).

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path procedures/icp_playbook.md --output json`
   *Governance: Validates ICP Playbook documentation exists.*

2. `aws codecommit get-file --repository-name security-governance --file-path procedures/incident-response-plan.md --output json`
   *Governance: Validates Incident Response Plan documentation exists.*

3. `aws sns list-topics --output json`
   *Infrastructure: Validates SNS topics exist for incident notifications.*

4. `aws sns list-subscriptions --output json`
   *Infrastructure: Validates SNS subscriptions are active/confirmed.*

## Latest Results

PASS Excellent 10/10 (100%): PASS [Governance] ICP Playbook verified (10426 bytes).
- PASS [Governance] IR Plan verified (5730 bytes).
- PASS [Infrastructure] 10 SNS Topic(s) found (2 incident-specific).
- PASS [Infrastructure] 6 Active SNS Subscription(s) found.

---
*Generated 2025-11-24 18:34 UTC*