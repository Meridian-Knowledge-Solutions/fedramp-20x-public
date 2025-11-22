# KSI-AFR-11: Ensure that cryptographic modules used to protect potentially sensitive federal customer data are selected and used in alignment with the FedRAMP 20x Using Cryptographic Modules (UCM) policy and persistently address all related requirements and recommendations.

## Overview

**Category:** Other
**Status:** FAIL
**Last Check:** 2025-11-22 18:24

**What it validates:** Ensure that cryptographic modules used to protect potentially sensitive federal customer data are selected and used in alignment with the FedRAMP 20x Using Cryptographic Modules (UCM) policy and persistently address all related requirements and recommendations.

**Why it matters:** Validates cryptographic module usage through aggregate KMS configuration, encryption-at-rest status, TLS policies, and UCM governance documentation.

## Validation Method

1. `aws kms list-aliases --output json`
   *Inventory: Lists all KMS key aliases. Validates cryptographic key management is active.*

2. `aws kms list-keys --output json`
   *Configuration: Counts total KMS keys. Validates key management infrastructure exists.*

3. `aws s3api list-buckets --output json`
   *S3 Inventory: Lists all S3 buckets for encryption validation.*

4. `aws s3api get-bucket-encryption --bucket meridian-fedramp-evidence --output json`
   *At-Rest Encryption: Validates primary evidence bucket uses AES256 or aws:kms encryption.*

5. `aws rds describe-db-instances --output json --query 'DBInstances[*].[DBInstanceIdentifier,StorageEncrypted,KmsKeyId]'`
   *Database Encryption: Validates all RDS instances have StorageEncrypted=true with KMS keys.*

6. `aws elbv2 describe-ssl-policies --output json`
   *Transit Encryption: Validates FIPS-compliant TLS policies are configured (TLS 1.2+).*

7. `aws elbv2 describe-load-balancers --output json --query 'LoadBalancers[*].[LoadBalancerName,Type]'`
   *Load Balancer Inventory: Lists ALB/NLB for SSL policy validation.*

8. `aws codecommit get-file --repository-name security-governance --file-path cryptography/UCM.md --output json`
   *Governance: Validates UCM policy document exists and is maintained.*

## Latest Results

- Error in wrapped function evaluate_KSI_AFR_11: 'str' object has no attribute 'get'

---
*Generated 2025-11-22 18:34 UTC*