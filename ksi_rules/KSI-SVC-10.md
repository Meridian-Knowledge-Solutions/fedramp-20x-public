# KSI-SVC-10: Perform regularly scheduled backups

## Overview

**Category:** Service Configuration
**Status:** PASS
**Last Check:** 2025-10-20 01:00

**What it validates:** Perform regularly scheduled backups

**Why it matters:** Validates that automated data lifecycle and retention policies are in place across AWS Backup, S3, and CloudWatch Logs.

## Validation Method

1. `aws backup get-backup-plan --backup-plan-id $(aws backup list-backup-plans --query 'BackupPlansList[0].BackupPlanId' --output text) --output json || echo '{"BackupPlan": null}'`
   *Validate that backup plans have defined retention and deletion lifecycles.*

2. `for b in $(aws s3api list-buckets --query 'Buckets[].Name' --output text); do echo "Bucket: $b"; aws s3api get-bucket-lifecycle-configuration --bucket "$b" --output json 2>/dev/null || echo 'No lifecycle'; done`
   *Check all S3 buckets for active lifecycle policies for data retention.*

3. `aws logs describe-log-groups --output json`
   *Verify that CloudWatch Log groups have retention policies configured.*

4. `aws lambda list-functions --output json`
   *Identify any custom Lambda functions used for automated data cleanup.*

## Latest Results

PASS Excellent automated data lifecycle management (100%): PASS [Backup Retention] AWS Backup plans have explicit deletion lifecycles, ensuring recovery points are removed as required.
- PASS [S3 Lifecycle] 1 S3 bucket(s) have active lifecycle policies to manage object expiration.
- PASS [Log Retention] A strong log retention strategy is in place, with 100% of log groups having a defined retention period.

---
*Generated 2025-10-20 01:00 UTC*