# KSI-RPL-01: Establish a recovery time objective (RTO) and recovery point objective (RPO) for the system

## Overview

**Category:** Recovery Planning
**Status:** PASS
<<<<<<< Updated upstream
**Last Check:** 2025-11-19 17:00
=======
**Last Check:** 2025-11-19 17:02
>>>>>>> Stashed changes

**What it validates:** Establish a recovery time objective (RTO) and recovery point objective (RPO) for the system

**Why it matters:** Validates RTO/RPO definition from basic backup schedules to enterprise-grade disaster recovery planning and business continuity governance

## Validation Method

1. `aws rds describe-db-instances --output json`
   *Check RDS backup configurations for RPO compliance*

2. `aws backup list-backup-plans --output json`
   *Validate AWS Backup plans for RTO/RPO objectives*

3. `aws ssm get-parameter --name '/backup/rto-objectives' --query 'Parameter.Value' --output text || echo 'Not configured'`
   *Check SSM Parameter Store for documented RTO objectives*

4. `aws ssm get-parameter --name '/backup/rpo-objectives' --query 'Parameter.Value' --output text || echo 'Not configured'`
   *Validate SSM Parameter Store for documented RPO objectives*

5. `aws backup describe-backup-vault --backup-vault-name default --output json || echo '{"BackupVault": null}'`
   *Check backup vault configuration for recovery capabilities*

6. `PLAN_ID=$(aws backup list-backup-plans --query 'BackupPlansList[0].BackupPlanId' --output text 2>/dev/null || echo 'none'); if [ "$PLAN_ID" != "none" ]; then aws backup list-backup-selections --backup-plan-id "$PLAN_ID" --output json; else echo '{"BackupSelectionsList": []}'; fi`
   *Validate backup plan resource selections for comprehensive coverage*

## Latest Results

PASS Excellent 16/17 (94%): PASS Database backup capability: Max retention meets/exceeds 7 days (7 days).
- PASS Point-in-time recovery: Enabled for 1/1 databases.
- PASS Backup infrastructure: 2 AWS Backup plan(s) configured.
- PASS Backup plan execution confirmed (at least one plan has run).
- PASS Defined RTO objectives found: '4 hours'.
- PASS Defined RPO objectives found: 'Not configured'.
- PASS Backup vault configured (1 vault(s) found).
- PASS Backup selection coverage: 1 backup selection(s) defined.

---
<<<<<<< Updated upstream
*Generated 2025-11-19 17:00 UTC*
=======
*Generated 2025-11-19 17:02 UTC*
>>>>>>> Stashed changes
