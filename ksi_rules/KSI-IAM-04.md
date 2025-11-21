# KSI-IAM-04: Use a least-privileged, role and attribute-based, and just-in-time security authorization model for all user and non-user accounts and services.

## Overview

**Category:** Identity and Access Management
**Status:** PASS
**Last Check:** 2025-11-21 06:24

**What it validates:** Use a least-privileged, role and attribute-based, and just-in-time security authorization model for all user and non-user accounts and services.

**Why it matters:** Validates comprehensive user role mapping from basic IAM groups to enterprise-grade permission sets and centralized access management

## Validation Method

1. `INSTANCE_ARN=$(aws sso-admin list-instances --query 'Instances[0].InstanceArn' --output text 2>/dev/null || echo 'none'); if [ "$INSTANCE_ARN" != "none" ]; then aws sso-admin list-permission-sets --instance-arn "$INSTANCE_ARN" --output json; else echo '{"PermissionSets": []}'; fi`
   *Check SSO permission sets for role-based access mapping*

2. `aws iam list-roles --output json`
   *Validate IAM roles with clear purpose and user mapping*

3. `aws iam list-users --output json`
   *Check IAM users and their role assignments*

4. `aws sts get-caller-identity --output json`
   *Validate current identity and role assumption*

5. `aws iam get-account-summary --output json`
   *Check account-level role and user statistics*

## Latest Results

PASS Excellent 10/10 (100%): PASS [Modern Auth] IAM Identity Center usage inferred from 3 SSO-managed roles.
- PASS [Role Mapping] Inferred 3 distinct permission sets (e.g., Development, AdministratorAccess, ReadOnlyAccess).
- PASS [Least Privilege] Excellent: 97 roles and 0 IAM users found (strong role-based pattern).
- PASS [Just-in-Time] Validation uses temporary credentials via an assumed role (best practice).

---
*Generated 2025-11-21 06:36 UTC*