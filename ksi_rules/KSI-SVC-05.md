# KSI-SVC-05: Use cryptographic methods to validate the integrity of machine-based information resources.

## Overview

**Category:** Service Configuration
**Status:** PASS
<<<<<<< Updated upstream
**Last Check:** 2025-11-23 06:18
=======
**Last Check:** 2025-11-23 06:41
>>>>>>> Stashed changes

**What it validates:** Use cryptographic methods to validate the integrity of machine-based information resources.

**Why it matters:** Validates comprehensive configuration monitoring from basic CloudTrail to enterprise-grade automated detection and response

## Validation Method

1. `aws cloudtrail describe-trails --output json`
   *Check CloudTrail for configuration change audit logging*

2. `aws kms list-keys --output json`
   *Validate KMS encryption for secure log storage*

3. `aws kms list-aliases --output json`
   *Check KMS key aliases for log encryption management*

4. `aws s3api list-buckets --output json`
   *Validate S3 buckets for CloudTrail log storage*

5. `aws rds describe-db-instances --output json`
   *Check RDS configuration change logging*

6. `aws configservice describe-configuration-recorders --output json`
   *Validate Config recorders for continuous configuration monitoring*

7. `aws cloudwatch describe-alarms --output json`
   *Check CloudWatch alarms for configuration change alerts*

8. `aws sns list-topics --output json`
   *Validate SNS topics for configuration change notifications*

9. `aws backup list-backup-vaults --output json`
   *Check backup configurations for disaster recovery*

10. `aws organizations describe-organization --output json`
   *Validate organization-wide configuration monitoring policies*

## Latest Results

PASS Excellent 20/20 (100%): PASS Audit integrity foundation: 1/1 CloudTrail trails with log file validation.
- PASS Cryptographic infrastructure: 17 KMS keys available.
- PASS Key management governance: 6 customer-managed KMS aliases.
- PASS Object integrity capability: 10 S3 buckets available for versioning and integrity protection.
- PASS Database integrity: 1/1 RDS instances with encrypted storage (protects data at rest).
- PASS Configuration integrity: 1 active Config recorders covering global & all supported types.
- PASS Backup integrity: 3/3 encrypted backup vaults.
- PASS Integrity monitoring: 13 CloudWatch alarms potentially related to integrity violations detected.
- PASS Integrity notification infrastructure: 10 SNS topics available for event communication.
- PASS Enterprise-wide integrity governance: AWS Organizations enables centralized policies.
- PASS Advanced organization features: SCPs for integrity policy enforcement enabled.

---
<<<<<<< Updated upstream
*Generated 2025-11-23 06:28 UTC*
=======
*Generated 2025-11-23 06:51 UTC*
>>>>>>> Stashed changes
