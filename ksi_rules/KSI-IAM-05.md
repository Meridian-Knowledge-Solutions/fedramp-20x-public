# KSI-IAM-05: Require phishing-resistant MFA for all user authentication to the cloud service offering and all customer information resources.

## Overview

**Category:** Identity and Access Management
**Status:** FAIL
**Last Check:** 2025-11-22 06:22

**What it validates:** Require phishing-resistant MFA for all user authentication to the cloud service offering and all customer information resources.

**Why it matters:** Validates phishing-resistant MFA (hardware tokens, FIDO2) from basic IAM MFA to enterprise-grade SSO integration with hardware token enforcement

## Validation Method

1. `aws iam list-users --output json`
   *List all IAM users to check MFA assignment*

2. `aws sso-admin list-instances --output json`
   *List ALL SSO instances for MFA policy validation*

3. `aws sso-admin list-instances --output json | jq -r '.Instances[].IdentityStoreId' | xargs -I {} aws identitystore list-users --identity-store-id {} --output json | jq -s '.' || echo '[]'`
   *Get users for ALL SSO/Identity Store instances - validates MFA enforcement across all identity sources*

4. `aws iam list-virtual-mfa-devices --output json`
   *Check virtual MFA devices (should flag if only virtual MFA, not phishing-resistant)*

5. `aws cloudtrail describe-trails --output json`
   *List ALL CloudTrail trails for MFA authentication logging*

6. `aws cloudtrail describe-trails --output json | jq -r '.trailList[].TrailARN' | xargs -I {} aws cloudtrail get-trail-status --name {} --output json | jq -s '.' || echo '[]'`
   *Get status for ALL CloudTrail trails - validates logging of all authentication events*

7. `aws iam get-account-password-policy --output json || echo '{"PasswordPolicy": null}'`
   *Validate password policy as defense-in-depth alongside MFA*

## Latest Results

FAIL Critical Zero Trust Gaps Detected (100%): FAIL [Monitoring] CRITICAL GAP: CloudTrail ('meridianks-Management-events') is configured but IS NOT LOGGING.
- PASS [Identity] Modern Zero Trust identity platform is in use (IAM Identity Center).
- WARNING [Segmentation] Security group data unavailable.

---
*Generated 2025-11-22 06:34 UTC*