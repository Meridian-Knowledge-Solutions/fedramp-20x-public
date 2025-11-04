# KSI-RPL-04: Test recovery procedures regularly

## Overview

**Category:** Recovery Planning
**Status:** PASS
<<<<<<< Updated upstream
**Last Check:** 2025-11-04 12:20
=======
**Last Check:** 2025-11-04 12:41
>>>>>>> Stashed changes

**What it validates:** Test recovery procedures regularly

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

PASS Good recovery testing capability established (57%): PASS Backup infrastructure validation: 50 recent backup operations prove recovery foundation
- PASS Point-in-time recovery testing capability: 1/1 databases ready for RPO validation
- PASS Automated recovery testing infrastructure available
- PASS Recovery test tracking: Last test execution tracked - Not configured

---
<<<<<<< Updated upstream
*Generated 2025-11-04 12:20 UTC*
=======
*Generated 2025-11-04 12:41 UTC*
>>>>>>> Stashed changes
