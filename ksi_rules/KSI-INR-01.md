# KSI-INR-01: Respond to incidents according to FedRAMP requirements and cloud service provider policies

## Overview

**Category:** Incident Reporting
**Status:** PASS
**Last Check:** 2025-11-19 20:13

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
   *Validate CloudTrail managed service for audit logging*

7. `aws cloudtrail get-trail-status --name $(aws cloudtrail describe-trails --query 'trailList[0].Name' --output text) --output json || echo '{"IsLogging": false}'`
   *Check active CloudTrail logging status*

8. `aws codecommit get-differences --repository-name security-governance --after-commit-specifier refs/heads/main --output json`
   *Check incident response plan maintenance*

## Latest Results

PASS Excellent 11/11 (100%): PASS Incident response plan documented in CodeCommit.
- PASS Incident response plan appears comprehensive (based on size >5KB).
- PASS Security Hub integration detected (50 findings tracked).
- PASS GuardDuty threat detection enabled (1 detectors).
- PASS CloudTrail audit logging configured (1 trails).
- PASS Incident response plan maintenance: 1 recent update(s) detected.

---
*Generated 2025-11-19 20:13 UTC*