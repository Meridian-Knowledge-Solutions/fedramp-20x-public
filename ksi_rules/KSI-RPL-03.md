# KSI-RPL-03: Regularly test the recovery planning capability by performing disaster recovery tests at least annually.

## Overview

**Category:** Recovery Planning
**Status:** PASS
<<<<<<< Updated upstream
**Last Check:** 2025-11-24 12:24
=======
**Last Check:** 2025-11-24 12:46
>>>>>>> Stashed changes

**What it validates:** Regularly test the recovery planning capability by performing disaster recovery tests at least annually.

**Why it matters:** Validates disaster recovery testing infrastructure via backup plans, job history, and resource snapshots.

## Validation Method

1. `aws backup list-backup-plans --output json`
   *List ALL backup plans.*

2. `aws backup list-backup-plans --output json | jq -r '.BackupPlansList[].BackupPlanId' | xargs -I {} aws backup get-backup-plan --backup-plan-id {} --output json | jq -s '.' || echo '[]'`
   *Get details for ALL backup plans.*

3. `aws backup list-backup-jobs --by-state COMPLETED --max-results 10 --output json`
   *REQUIRED: Validate successful backup execution history.*

4. `aws ec2 describe-snapshots --owner-ids self --max-results 10 --output json`
   *REQUIRED: Validate existence of EBS snapshots.*

5. `aws rds describe-db-instances --output json`
   *REQUIRED: Validate RDS automated backup settings.*

6. `aws lambda list-functions --query 'Functions[?contains(FunctionName, `backup`) || contains(FunctionName, `recovery`)]' --output json`
   *Validate Lambda functions for automated DR testing.*

## Latest Results

PASS Excellent 10/10 (100%): PASS [Retention] All 2 backup plans meet retention requirements (>28 days).
- PASS [Execution] 10 successful backup jobs detected in the last 7 days.
- PASS [Coverage] 1/1 RDS instances have automated backups enabled.
- PASS [Coverage] 10 EBS snapshots available as recovery points.

---
<<<<<<< Updated upstream
*Generated 2025-11-24 12:34 UTC*
=======
*Generated 2025-11-24 12:56 UTC*
>>>>>>> Stashed changes
