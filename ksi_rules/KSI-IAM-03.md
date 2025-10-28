# KSI-IAM-03: Implement least privilege access via role-based access control policies

## Overview

**Category:** Identity and Access Management
**Status:** PASS
**Last Check:** 2025-10-28 18:55

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

PASS Excellent role-based access control (80%): PASS [Roles] Excellent role-based foundation with 92 IAM roles available for secure, temporary credentials.
- PASS [EC2 Security] Best practice followed: All 6 running instances use IAM Instance Profiles.
- WARNING [IAM Hygiene] 1 IAM user(s) with console passwords exist. Transitioning to a fully federated model is recommended.

---
*Generated 2025-10-28 18:55 UTC*