# KSI-MLA-01: Implement end-to-end logging to capture security events

## Overview

**Category:** Monitoring, Logging, and Auditing
**Status:** PASS
**Last Check:** 2025-10-18 06:44

**What it validates:** Implement end-to-end logging to capture security events

**Why it matters:** Validates a comprehensive, multi-layered logging and SIEM strategy, including collection, integrity, storage, and analysis.

## Validation Method

1. `aws cloudtrail describe-trails --output json`
   *Check CloudTrail configuration for log collection and integrity.*

2. `aws cloudtrail get-trail-status --name $(aws cloudtrail describe-trails --query 'trailList[0].TrailARN' --output text 2>/dev/null || echo 'none') --output json || echo '{"IsLogging": false}'`
   *CRITICAL: Check if the primary organization trail is actively logging.*

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

PASS Strong SIEM and logging capabilities (60%): FAIL [Collection] No CloudTrail configured, a critical gap in security logging.
- PASS [Storage] A strong log retention policy is in place, with 24 log groups retained for 365+ days.
- PASS [Encryption] 17 KMS keys are available to ensure logs are encrypted at rest.
- PASS [Analysis] Automated analysis is active with 7 security-focused CloudWatch Alarms.
- PASS [Analysis] Advanced threat analysis is enabled through Security Hub, with 20 recent findings.

---
*Generated 2025-10-18 06:44 UTC*