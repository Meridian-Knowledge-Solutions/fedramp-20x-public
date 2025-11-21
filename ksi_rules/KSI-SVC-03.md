# KSI-SVC-03: Encrypt data at rest

## Overview

**Category:** Service Configuration
**Status:** Not validated

**What it validates:** Encrypt data at rest

**Why it matters:** Validates comprehensive data at rest encryption from basic S3 encryption to enterprise-grade KMS key management and compliance

## Validation Method

1. `aws s3api list-buckets --output json`
   *Check S3 buckets for default encryption configurations*

2. `aws ec2 describe-volumes --output json`
   *Validate EBS volume encryption at rest*

3. `aws rds describe-db-instances --output json`
   *Check RDS database encryption at rest*

4. `aws rds describe-db-snapshots --output json`
   *Validate RDS snapshot encryption*

5. `aws dynamodb list-tables --output json`
   *Check DynamoDB tables for encryption at rest*

6. `aws elasticache describe-cache-clusters --output json`
   *Validate ElastiCache encryption at rest*

7. `aws redshift describe-clusters --output json`
   *Check Redshift cluster encryption*

8. `aws backup list-backup-vaults --output json`
   *Validate AWS Backup vault encryption*

9. `aws kms list-keys --output json`
   *Check KMS key usage for data encryption*

10. `aws organizations describe-organization --output json`
   *Validate organization-wide encryption at rest policies*

---
*Generated 2025-11-21 02:59 UTC*