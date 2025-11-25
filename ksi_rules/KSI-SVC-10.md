# KSI-SVC-10: Remove unwanted federal customer data promptly when requested by an agency in alignment with customer agreements, including from backups if appropriate.

## Overview

**Category:** Service Configuration
**Status:** PASS
**Last Check:** 2025-11-25 02:46

**What it validates:** Remove unwanted federal customer data promptly when requested by an agency in alignment with customer agreements, including from backups if appropriate.

**Why it matters:** Validates that automated data lifecycle and retention policies are in place across AWS Backup, S3, and CloudWatch Logs.

## Validation Method

1. `aws backup list-backup-plans --output json`
   *List ALL backup plans to validate data retention policies across all plans*

2. `aws backup list-backup-plans --output json | jq -r '.BackupPlansList[].BackupPlanId' | xargs -I {} aws backup get-backup-plan --backup-plan-id {} --output json | jq -s '.' || echo '[]'`
   *Get details for ALL backup plans - validates deletion lifecycles and retention policies*

3. `for b in $(aws s3api list-buckets --query 'Buckets[].Name' --output text); do echo "Bucket: $b"; aws s3api get-bucket-lifecycle-configuration --bucket "$b" --output json 2>/dev/null || echo 'No lifecycle'; done`
   *Check all S3 buckets for active lifecycle policies for data retention*

4. `aws logs describe-log-groups --output json`
   *Verify that CloudWatch Log groups have retention policies configured*

5. `aws lambda list-functions --output json`
   *Identify any custom Lambda functions used for automated data cleanup*

## Latest Results

PASS Sufficient 7/10 (70%): PASS [Backup Retention] All 2 backup plan(s) have explicit deletion lifecycle rules.
- INFO [S3 Lifecycle] No active S3 lifecycle policies found.
- PASS [Log Retention] Strong coverage: 31/33 (94%) log groups have retention policies.

---
*Generated 2025-11-25 02:57 UTC*