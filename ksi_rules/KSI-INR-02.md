# KSI-INR-02: Maintain a log of incidents and periodically review past incidents for patterns or vulnerabilities.

## Overview

**Category:** Incident Reporting
**Status:** PASS
**Last Check:** 2025-11-23 00:44

**What it validates:** Maintain a log of incidents and periodically review past incidents for patterns or vulnerabilities.

**Why it matters:** Validates insider threat detection from basic access monitoring to enterprise-grade behavioral analytics and automated threat detection

## Validation Method

1. `aws events list-rules --output json`
   *Check EventBridge rules for insider threat detection automation*

2. `aws logs describe-log-groups --output json`
   *Validate CloudWatch Logs for insider threat monitoring*

3. `aws guardduty list-detectors --output json`
   *Check GuardDuty for insider threat detection capabilities*

4. `aws securityhub get-findings --max-results 5 --output json`
   *Validate Security Hub findings for insider threat alerts*

5. **Manual Review:** Manual review of insider threat program documentation, detection rules, and response procedures

## Latest Results

PASS Excellent 10/10 (100%): PASS Incident response infrastructure fully configured (4/4 components found).
- PASS Operational log artifact ('incident_database.csv') found and valid (1 incidents).
- PASS Periodic review report artifact ('quarterly_incident_review_minutes.md') found and appears valid.

---
*Generated 2025-11-23 00:55 UTC*