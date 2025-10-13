# KSI-IAM-03: Implement least privilege access via role-based access control policies

## Overview

**Category:** Identity and Access Management
**Status:** FAIL
**Last Check:** 2025-10-13 12:35

**What it validates:** Implement least privilege access via role-based access control policies

**Why it matters:** Validates the use of IAM roles for services and EC2, and critically fails if IAM users are used for service accounts, checking their attached policies for risk assessment.

## Validation Method

1. `aws iam list-roles --output json`
   *Check for a strong foundation of IAM roles for service authentication.*

2. `aws iam list-users --output json`
   *Identify all traditional IAM users for analysis.*

3. `aws ec2 describe-instances --query 'Reservations[*].Instances[*].IamInstanceProfile.Arn' --output json`
   *Verify that all running EC2 instances are using IAM roles.*

4. `for user in $(aws iam list-users --query 'Users[].UserName' --output text); do echo "User: $user"; aws iam list-attached-user-policies --user-name "$user" --output json; done`
   *CRITICAL: Check for policies attached directly to IAM users, which is an anti-pattern for service accounts.*

## Latest Results

FAIL Immediate Failure: Insecure service authentication methods detected. CRITICAL: IAM user 'change_template_approver' appears to be a service account. This is a high-risk anti-pattern
- replace with an IAM role.
- CRITICAL: IAM user 'Terraform' appears to be a service account. This is a high-risk anti-pattern
- replace with an IAM role.

---
*Generated 2025-10-13 12:35 UTC*