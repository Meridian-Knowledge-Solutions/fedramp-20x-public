# KSI-IAM-03: Enforce appropriately secure authentication methods for non-user accounts and services.

## Overview

**Category:** Identity and Access Management
**Status:** PASS
**Last Check:** 2025-11-24 04:30

**What it validates:** Enforce appropriately secure authentication methods for non-user accounts and services.

**Why it matters:** Fails immediately if any IAM user exists without a console password, as this indicates a service account using insecure, long-lived credentials. It then scores the account based on its adoption of IAM roles.

## Validation Method

1. `aws iam list-roles --output json`
   *Check for a strong foundation of IAM roles for service authentication.*

2. `aws iam list-users --output json`
   *Identify all traditional IAM users for analysis.*

3. `aws ec2 describe-instances --output json`
   *Verify that all running EC2 instances are using IAM roles (Provides full instance data).*

4. `for user in $(aws iam list-users --query 'Users[].UserName' --output text 2>/dev/null || echo ''); do aws iam get-login-profile --user-name "$user" --output json 2>/dev/null || true; done`
   *CRITICAL: Check for console passwords. A failure here for a user implies they *lack* a password (service user anti-pattern).*

## Latest Results

PASS Excellent 10/10 (100%): PASS [Roles] Excellent role-based foundation with 97 IAM roles available for secure, temporary credentials.
- PASS [EC2 Security] Best practice followed: All 6 running instances use IAM Instance Profiles.
- PASS [IAM Hygiene] Excellent: No IAM human users with console access found. Access likely managed via federation or roles.

---
*Generated 2025-11-24 04:38 UTC*