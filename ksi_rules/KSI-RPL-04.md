# KSI-RPL-04: Regularly test the capability to recover from incidents and contingencies.

## Overview

**Category:** Recovery Planning
**Status:** PASS
<<<<<<< Updated upstream
**Last Check:** 2025-11-23 00:44
=======
**Last Check:** 2025-11-23 01:08
>>>>>>> Stashed changes

**What it validates:** Regularly test the capability to recover from incidents and contingencies.

**Why it matters:** Validates recovery testing by checking for recent, successful backup jobs, RDS point-in-time recovery (PITR) capability, and by parsing CloudWatch logs from the 'fedramp-backup-restore' Lambda to confirm successful automated test execution.

## Validation Method

1. `aws backup list-backup-jobs --by-state COMPLETED --by-created-after $(date -u -d '30 days ago' +%Y-%m-%dT%H:%M:%SZ 2>/dev/null || date -u -v-30d +%Y-%m-%dT%H:%M:%SZ) --max-results 50 --output json`
   *Validate recent backup jobs for recovery readiness*

2. `aws rds describe-db-instances --query 'DBInstances[*].[DBInstanceIdentifier,LatestRestorableTime]' --output json`
   *Check RDS latest restorable time for point-in-time recovery testing*

3. `aws lambda get-function --function-name fedramp-backup-restore --output json || echo '{"Configuration": null}'`
   *Verify the automated recovery testing Lambda function exists.*

4. `aws logs filter-log-events --log-group-name /aws/lambda/fedramp-backup-restore --filter-pattern '?"Validation Summary:" ?"restore job(s) failed!"' --start-time $(date -u -d '7 days ago' +%s000 2>/dev/null || date -u -v-7d +%s000) --output json`
   *Get recent recovery test summary and failure logs from the Lambda.*

## Latest Results

PASS Strong 8/10 (80%): PASS [Backup Success] 39 successful backup jobs completed in the last 72 hours.
- PASS [Backup Encryption] All recent backup jobs are encrypted.
- PASS [Backup Retention] All recent backup jobs have a retention lifecycle.
<<<<<<< Updated upstream
- PASS [PITR] RDS instance 'saas' has Point-in-Time-Recovery enabled (Last restorable: 2025-11-23T00:35:01+00:00).
=======
- PASS [PITR] RDS instance 'saas' has Point-in-Time-Recovery enabled (Last restorable: 2025-11-23T01:00:01+00:00).
>>>>>>> Stashed changes
- PASS [Automation] Found automated recovery Lambda: 'fedramp-backup-restore'
- WARNING [Recovery Test] Recovery Lambda exists but has not logged any validation summaries in the last 7 days.

---
<<<<<<< Updated upstream
*Generated 2025-11-23 00:55 UTC*
=======
*Generated 2025-11-23 01:18 UTC*
>>>>>>> Stashed changes
