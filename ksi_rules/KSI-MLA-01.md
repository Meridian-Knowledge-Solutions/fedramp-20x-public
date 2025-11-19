# KSI-MLA-01: Implement end-to-end logging to capture security events

## Overview

**Category:** Monitoring, Logging, and Auditing
**Status:** PASS
<<<<<<< Updated upstream
**Last Check:** 2025-11-19 12:14
=======
**Last Check:** 2025-11-19 12:24
>>>>>>> Stashed changes

**What it validates:** Implement end-to-end logging to capture security events

**Why it matters:** Validates a comprehensive, multi-layered logging architecture, including active collection, integrity, retention, and analysis.

## Validation Method

1. `aws cloudtrail describe-trails --output json`
   *Validate CloudTrail managed service for audit logging*

2. `aws cloudtrail get-trail-status --name $(aws cloudtrail describe-trails --query 'trailList[0].TrailARN' --output text) --output json || echo '{"IsLogging": false}'`
   *Check active CloudTrail logging status (using ARN to prevent errors)*

3. `aws logs describe-log-groups --output json`
   *Validate centralized log storage and retention policies in CloudWatch.*

4. `aws cloudwatch describe-alarms --output json`
   *Check for automated log analysis and alerting on security events.*

5. `aws kms list-keys --output json`
   *Validate use of KMS for log encryption at rest.*

6. `aws securityhub get-findings --max-results 20 --output json`
   *Validate Security Hub for advanced, aggregated security findings.*

7. `aws organizations describe-organization --output json`
   *Confirm an enterprise governance structure for centralized logging.*

## Latest Results

PASS Excellent 10/10 (100%): PASS [Collection] CloudTrail (meridianks-Management-events) is actively logging events.
- PASS [Collection] Trail scope includes entire organization.
- PASS [Integrity] CloudTrail logs are tamper-resistant (validation), encrypted (KMS), and centrally managed (Org trail).
- PASS [Storage] Strong log retention policy: 26/33 log groups retained >= 365 days.
- PASS [Encryption] 17 KMS keys available (can be used for log encryption).
- PASS [Analysis] Automated analysis likely active via 13 security-focused CloudWatch Alarms.
- PASS [Analysis] Advanced threat analysis potentially enabled via Security Hub (20 recent findings detected).

---
<<<<<<< Updated upstream
*Generated 2025-11-19 12:14 UTC*
=======
*Generated 2025-11-19 12:24 UTC*
>>>>>>> Stashed changes
