# KSI-SVC-06: Automate management, protection, and regular rotation of digital keys, certificates, and other secrets.

## Overview

**Category:** Service Configuration
**Status:** PASS
**Last Check:** 2025-11-23 02:56

**What it validates:** Automate management, protection, and regular rotation of digital keys, certificates, and other secrets.

**Why it matters:** Validates comprehensive key management from basic KMS to enterprise-grade certificate lifecycle, rotation, and cryptographic compliance

## Validation Method

1. `aws kms list-keys --output json`
   *Check KMS keys for centralized encryption key management*

2. `aws acm list-certificates --output json`
   *Validate ACM certificates for centralized certificate management*

3. `aws kms list-aliases --output json`
   *Check KMS key aliases for key organization and management*

4. `aws ssm describe-parameters --parameter-filters Key=Type,Values=SecureString --output json`
   *Validate SSM SecureString parameters using KMS encryption*

5. `aws secretsmanager list-secrets --output json`
   *Check Secrets Manager for KMS-encrypted secret storage*

6. `aws iam list-server-certificates --output json`
   *Validate IAM server certificates and migration to ACM*

7. `aws cloudformation list-stacks --stack-status-filter CREATE_COMPLETE UPDATE_COMPLETE --output json`
   *Check CloudFormation for infrastructure as code key management*

8. `aws cloudtrail lookup-events --lookup-attributes AttributeKey=ResourceType,AttributeValue=AWS::KMS::Key --max-items 20 --output json`
   *Validate CloudTrail audit logs for key usage and management*

9. `aws organizations describe-organization --output json`
   *Check organization-wide centralized key management policies*

## Latest Results

PASS Excellent 18/20 (90%): PASS Automated key management infrastructure: 17 KMS keys detected.
- PASS Automated certificate management: 2/2 ACM certificates are ISSUED.
- PASS Key governance structure: 6 customer-managed KMS aliases found.
- PASS Automated encryption integration: 4 SecureString parameters found (implies KMS usage).
- PASS Secrets management in use: 2 secrets found in Secrets Manager.
- PASS Modern certificate management: No legacy IAM server certificates found.
- PASS Infrastructure as Code key management: 14/14 successful CloudFormation stacks (implies IaC practices).
- PASS Key management audit trail: 20 recent key management events tracked via CloudTrail lookup.
- PASS Enterprise-wide key management governance: AWS Organizations enables centralized key policies.
- PASS Advanced organization features: SCPs for key management policy enforcement enabled.

---
*Generated 2025-11-23 03:06 UTC*