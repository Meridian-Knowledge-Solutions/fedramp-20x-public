# KSI-MLA-01: Log all activity on all information resources supporting the cloud service offering to a protected audit log in at least one location.

## Overview

**Category:** Monitoring, Logging, and Auditing
**Status:** PASS
**Last Check:** 2025-11-22 18:24

**What it validates:** Log all activity on all information resources supporting the cloud service offering to a protected audit log in at least one location.

**Why it matters:** Validates comprehensive audit logging from basic CloudTrail to enterprise-grade multi-region, organization-wide logging with S3/CloudWatch integration and log file validation

## Validation Method

1. `aws cloudtrail describe-trails --output json`
   *List ALL CloudTrail trails to ensure comprehensive audit coverage*

2. `aws cloudtrail describe-trails --output json | jq -r '.trailList[].TrailARN' | xargs -I {} aws cloudtrail get-trail-status --name {} --output json | jq -s '.' || echo '[]'`
   *Get status for ALL CloudTrail trails - validates logging is active and audit logs are being collected*

3. `aws s3api list-buckets --output json`
   *Check S3 buckets for audit log storage*

4. `aws logs describe-log-groups --output json`
   *Validate CloudWatch Logs for centralized audit log aggregation*

5. `aws kms list-aliases --output json`
   *Check KMS keys for audit log encryption*

6. `aws guardduty list-detectors --output json`
   *Validate GuardDuty for threat detection on audit logs*

7. `aws organizations describe-organization --output json`
   *Check organization-wide audit logging policies*

## Latest Results

PASS Strong 8/10 (80%): PASS [Collection] All 1 CloudTrail trails are actively logging.
- PASS [Integrity] All 1 trails have Validation and Encryption enabled.
- PASS [Storage] 26/33 log groups have long-term retention (>= 365 days).
- INFO [Analysis] No security-specific alarms or Security Hub findings detected.

---
*Generated 2025-11-22 18:34 UTC*