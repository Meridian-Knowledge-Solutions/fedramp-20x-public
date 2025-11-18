# KSI-IAM-04: Clearly define user roles and implement user-to-role mapping

## Overview

**Category:** Identity and Access Management
**Status:** PASS
**Last Check:** 2025-11-18 20:13

**What it validates:** Clearly define user roles and implement user-to-role mapping

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

PASS Excellent role-based authorization model (100%): PASS [Modern Auth] IAM Identity Center is in use, inferred from 3 SSO-managed roles.
- PASS [Role Mapping] Found 3 distinct permission sets (e.g., AdministratorAccess, Development, ReadOnlyAccess).
- INFO The direct SSO API call failed due to permissions, but role-based evidence confirms a modern setup.
- PASS [Least Privilege] Excellent role-to-user ratio (92 roles to 0 users) indicates a strong role-based access pattern.
- PASS [Just-in-Time] The validation process is using temporary credentials via an assumed role, following best practices.

---
*Generated 2025-11-18 20:13 UTC*