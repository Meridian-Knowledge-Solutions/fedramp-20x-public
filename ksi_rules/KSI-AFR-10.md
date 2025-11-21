# KSI-AFR-10: Integrate FedRAMP's Incident Communications Procedures (ICP) into incident response procedures and persistently address all related requirements and recommendations.

## Overview

**Category:** Other
**Status:** PASS
**Last Check:** 2025-11-21 04:15

**What it validates:** Integrate FedRAMP's Incident Communications Procedures (ICP) into incident response procedures and persistently address all related requirements and recommendations.

**Why it matters:** Validates the existence of BOTH the ICP Playbook and the Incident Response Plan.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path procedures/icp_playbook.md`
   *Check for ICP Playbook.*

2. `aws codecommit get-file --repository-name security-governance --file-path procedures/incident-response-plan.md`
   *Check for Incident Response Plan.*

## Latest Results

PASS Excellent 10/10 (100%): PASS [Documentation] ICP Playbook found in CodeCommit.
- PASS [Quality] Document appears substantial (10459 bytes).
- PASS [Documentation] Incident Response Plan found in CodeCommit.
- PASS [Quality] Document appears substantial (5730 bytes).

---
*Generated 2025-11-21 04:27 UTC*