# KSI-AFR-10: Integrate FedRAMP's Incident Communications Procedures (ICP) into incident response procedures and infrastructure.

## Overview

**Category:** Other
**Status:** FAIL
**Last Check:** 2025-11-22 18:24

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

- Error in wrapped function evaluate_KSI_AFR_10: 'str' object has no attribute 'get'

---
*Generated 2025-11-22 18:34 UTC*