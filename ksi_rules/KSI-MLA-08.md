# KSI-MLA-08: Protect audit logs to support after-the-fact investigations

## Overview

**Category:** Monitoring, Logging, and Auditing
**Status:** PASS
**Last Check:** 2025-10-20 06:48

**What it validates:** Protect audit logs to support after-the-fact investigations

**Why it matters:** Validates a multi-layered log protection strategy, including log integrity (CloudTrail), long-term retention and encryption (CloudWatch, KMS), and restricted access (IAM RBAC).

## Validation Method

1. `aws cloudtrail describe-trails --output json`
   *Validate the integrity and encryption of the primary audit log source (CloudTrail).*

2. `aws logs describe-log-groups --output json`
   *Check CloudWatch Logs for evidence of long-term, compliance-grade retention.*

3. `aws iam list-roles --output json`
   *Check for specialized IAM roles that enforce least privilege for log access.*

4. `aws kms list-keys --output json`
   *Verify that KMS keys are available for encrypting logs at rest.*

## Latest Results

PASS Excellent audit log protection (100%): PASS [Integrity] The primary CloudTrail has log file validation enabled, ensuring logs are tamper-resistant.
- PASS [Encryption] The primary CloudTrail is encrypted at rest using a KMS key.
- PASS [Retention] An excellent log retention policy is in place, with 24 log groups configured for 365+ days.
- PASS [Access Control] Excellent RBAC for logs detected, with distinct roles for administration (1) and viewing (2).

---
*Generated 2025-10-20 06:48 UTC*