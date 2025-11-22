# KSI-IAM-04: Require a centralized identity management system.

## Overview

**Category:** Identity and Access Management
**Status:** PASS
**Last Check:** 2025-11-22 16:22

**What it validates:** Require a centralized identity management system.

**Why it matters:** Validates centralized identity management via SSO instances, role inference, and caller identity.

## Validation Method

1. `aws sso-admin list-instances --output json`
   *List ALL SSO instances.*

2. `aws sso-admin list-instances --output json | jq -r '.Instances[].InstanceArn' | xargs -I {} aws sso-admin list-permission-sets --instance-arn {} --output json | jq -s '.' || echo '[]'`
   *Get permission sets (May fail if permissions restricted).*

3. `aws iam list-users --output json`
   *Check for local IAM users.*

4. `aws iam get-account-summary --output json`
   *Validate account-wide IAM posture.*

5. `aws organizations list-accounts --output json`
   *Check organization accounts.*

6. `aws iam list-roles --output json`
   *REQUIRED: List roles to infer SSO usage if API access is blocked.*

7. `aws sts get-caller-identity --output json`
   *REQUIRED: Validate current session is temporary (JIT).*

## Latest Results

PASS Excellent 10/10 (100%): PASS [Modern Auth] IAM Identity Center active: 1 instance(s) found.
- WARNING [Role Mapping] Could not list Permission Sets (AccessDenied). Attempting inference via Roles...
- PASS [Role Mapping] Inferred 3 Permission Sets from role list (e.g., ReadOnlyAccess).
- PASS [Least Privilege] Excellent: 97 roles and 0 IAM users (Pure RBAC).
- PASS [Just-in-Time] Validation performed via temporary credentials (assumed role).

---
*Generated 2025-11-22 16:32 UTC*