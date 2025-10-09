# KSI-INR-01: RESPOND to incidents according to FedRAMP requirements and cloud service provider policies

## Overview

**Category:** Incident Reporting
**Status:** FAIL
**Last Check:** 2025-10-09 20:38

**What it validates:** RESPOND to incidents according to FedRAMP requirements and cloud service provider policies

**Why it matters:** RFC-0014 Phase Two: Changed from 'Report' to 'Respond'. Validates FedRAMP-compliant incident RESPONSE procedures (broader than just reporting) in CodeCommit with Security Hub integration.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path procedures/incident-response.md --output json`
   *Retrieve incident RESPONSE procedures (not just reporting)*

2. `aws codecommit get-folder --repository-name security-governance --folder-path templates/incident/ --output json`
   *List incident notification templates*

3. `aws securityhub describe-hub --output json`
   *Validate Security Hub integration for incident response*

4. `aws securityhub get-findings --max-results 10 --output json`
   *Check active security findings tracking*

## Latest Results

FAIL Insufficient FedRAMP incident response (2/11): PASS Security Hub integrated: 0 findings tracked
- PASS Security Hub integrated: 10 findings tracked
- WARNING Legacy incident procedures - migrate to CodeCommit

---
*Generated 2025-10-09 20:38 UTC*