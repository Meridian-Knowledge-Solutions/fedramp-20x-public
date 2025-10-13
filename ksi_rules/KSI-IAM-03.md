# KSI-IAM-03: Implement least privilege access via role-based access control policies

## Overview

**Category:** Identity and Access Management
**Status:** FAIL
**Last Check:** 2025-10-13 22:44

**What it validates:** Implement least privilege access via role-based access control policies

**Why it matters:** Fails immediately if any IAM user exists without a console password, as this indicates a service account using insecure, long-lived credentials. It then scores the account based on its adoption of IAM roles.

## Validation Method

1. `aws iam list-roles --output json`
   *Check for a strong foundation of IAM roles for service authentication.*

2. `aws iam list-users --output json`
   *Identify all traditional IAM users for analysis.*

3. `aws ec2 describe-instances --query 'Reservations[*].Instances[*].IamInstanceProfile.Arn' --output json`
   *Verify that all running EC2 instances are using IAM roles.*

4. `for user in $(aws iam list-users --query 'Users[].UserName' --output text); do aws iam get-login-profile --user-name "$user" --output json; done`
   *CRITICAL: Check for console passwords. A failure for any user indicates a service account, which is an anti-pattern.*

## Latest Results

FAIL Immediate Failure: Insecure service authentication methods detected. CRITICAL: IAM user 'ReadOnly' is operating as a service account (no console password). This high-risk anti-pattern must be replaced with an IAM role.
- CRITICAL: IAM user 'change_template_approver' is operating as a service account (no console password). This high-risk anti-pattern must be replaced with an IAM role.
- CRITICAL: IAM user 'Terraform' is operating as a service account (no console password). This high-risk anti-pattern must be replaced with an IAM role.

---
*Generated 2025-10-13 22:44 UTC*