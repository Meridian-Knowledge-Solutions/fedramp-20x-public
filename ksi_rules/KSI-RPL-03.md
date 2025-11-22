# KSI-RPL-03: Regularly test the recovery planning capability by performing disaster recovery tests at least annually.

## Overview

**Category:** Recovery Planning
**Status:** FAIL
**Last Check:** 2025-11-22 06:22

**What it validates:** Regularly test the recovery planning capability by performing disaster recovery tests at least annually.

**Why it matters:** Validates disaster recovery testing infrastructure from basic backup testing to enterprise-grade automated DR validation with cross-region recovery

## Validation Method

1. `aws backup list-backup-plans --output json`
   *List ALL backup plans to ensure comprehensive DR coverage*

2. `aws backup list-backup-plans --output json | jq -r '.BackupPlansList[].BackupPlanId' | xargs -I {} aws backup get-backup-plan --backup-plan-id {} --output json | jq -s '.' || echo '[]'`
   *Get details for ALL backup plans - validates recovery testing schedules and procedures*

3. `aws backup list-recovery-points-by-backup-vault --backup-vault-name Default --output json || echo '{"RecoveryPoints": []}'`
   *Check recovery points for DR testing capability*

4. `aws lambda list-functions --query 'Functions[?contains(FunctionName, `backup`) || contains(FunctionName, `recovery`)]' --output json`
   *Validate Lambda functions for automated DR testing*

5. `aws cloudwatch describe-alarms --output json`
   *Check CloudWatch alarms for backup and recovery monitoring*

## Latest Results

FAIL Insufficient 5/10 (50%): PASS [Retention] All 2 backup plans meet retention requirements (>28 days).
- WARNING [Execution] Backup job history unavailable.

---
*Generated 2025-11-22 06:34 UTC*