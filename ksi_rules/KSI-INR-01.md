# KSI-INR-01: Respond to incidents according to FedRAMP requirements and cloud service provider policies

## Overview

**Category:** Incident Reporting
**Status:** PASS
**Last Check:** 2025-10-19 06:44

**What it validates:** Respond to incidents according to FedRAMP requirements and cloud service provider policies

**Why it matters:** Validates incident response procedures in version-controlled repository with FedRAMP-compliant notification timelines and AWS-specific containment actions.

## Validation Method

1. `aws codecommit get-repository --repository-name security-governance --output json`
   *Verify security-governance repository exists*

2. `aws codecommit get-file --repository-name security-governance --file-path procedures/incident-response-plan.md --output json`
   *Retrieve incident response plan document*

3. `aws codecommit get-folder --repository-name security-governance --folder-path procedures/ --output json`
   *List incident response procedures*

4. `aws securityhub get-findings --max-results 50 --output json`
   *Verify Security Hub findings tracking*

5. `aws guardduty list-detectors --output json`
   *Verify GuardDuty threat detection enabled*

6. `aws cloudtrail describe-trails --output json`
   *Verify CloudTrail audit logging for incident investigation*

7. `aws codecommit get-differences --repository-name security-governance --after-commit-specifier refs/heads/main --output json`
   *Check incident response plan maintenance*

## Latest Results

PASS Comprehensive FedRAMP incident response (10/11): PASS Incident response plan documented in CodeCommit
- PASS Comprehensive incident response procedures
- PASS Security Hub integrated: 50 findings tracked
- PASS GuardDuty threat detection enabled
- PASS Incident response plan maintenance: 1 updates

---
*Generated 2025-10-19 06:44 UTC*