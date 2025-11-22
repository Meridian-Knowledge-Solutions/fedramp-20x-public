# KSI-SVC-10: Remove unwanted federal customer data promptly when requested by an agency in alignment with customer agreements, including from backups if appropriate.

## Overview

**Category:** Service Configuration
**Status:** FAIL
**Last Check:** 2025-11-22 00:20

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

Below threshold: 6/10 (60.0%) - requires 64.0% for MODERATE impact: WARNING [Backup Retention] AWS Backup plan data unavailable.
- PASS [S3 Lifecycle] 4 S3 bucket(s) have active lifecycle policies with object expiration/cleanup.
- PASS [Log Retention] Strong log retention strategy: 31/33 (94%) log groups have a defined retention period.

---
*Generated 2025-11-22 00:33 UTC*