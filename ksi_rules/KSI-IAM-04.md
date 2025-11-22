# KSI-IAM-04: Require a centralized identity management system.

## Overview

**Category:** Identity and Access Management
**Status:** FAIL
**Last Check:** 2025-11-22 02:45

**What it validates:** Require a centralized identity management system.

**Why it matters:** Validates centralized identity management from basic AWS SSO to enterprise-grade SCIM automation with MFA enforcement and cross-account access

## Validation Method

1. `aws sso-admin list-instances --output json`
   *List ALL SSO instances (typically 1, but validates all for multi-org deployments)*

2. `aws sso-admin list-instances --output json | jq -r '.Instances[].InstanceArn' | xargs -I {} aws sso-admin list-permission-sets --instance-arn {} --output json | jq -s '.' || echo '[]'`
   *Get permission sets for ALL SSO instances - validates centralized access management*

3. `aws iam list-users --output json`
   *Check for local IAM users (should be minimal with SSO)*

4. `aws iam get-account-summary --output json`
   *Validate account-wide IAM posture and user counts*

5. `aws organizations list-accounts --output json`
   *Check organization accounts for centralized identity management*

## Latest Results

Below threshold: 6/10 (60.0%) - requires 64.0% for MODERATE impact: PASS [Modern Auth] IAM Identity Center active: 1 instance(s) found.
- PASS [Least Privilege] Excellent: 97 roles and 0 IAM users (Pure Role-Based Access).
- WARNING [Just-in-Time] Caller identity unavailable.

---
*Generated 2025-11-22 02:58 UTC*