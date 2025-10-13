# KSI-CNA-04: Use immutable infrastructure with strictly defined functionality and privileges

## Overview

**Category:** Cloud Native Architecture
**Status:** FAIL
**Last Check:** 2025-10-13 12:35

**What it validates:** Use immutable infrastructure with strictly defined functionality and privileges

**Why it matters:** Validates a hybrid infrastructure model by checking for serverless adoption, EC2 immutability patterns, least privilege violations (for both users and roles), and network security.

## Validation Method

1. `aws ec2 describe-instances --filters 'Name=instance-state-name,Values=running' --output json`
   *Check running instances for IaC management tags and age.*

2. `aws ec2 describe-launch-templates --output json`
   *Validate if EC2 instances are standardized via Launch Templates.*

3. `aws autoscaling describe-auto-scaling-groups --output json`
   *Check if EC2 instances use Auto Scaling for immutable scaling.*

4. `aws lambda list-functions --output json`
   *Validate adoption of inherently immutable serverless functions.*

5. `aws s3api list-buckets --query 'Buckets[?contains(Name, `terraform`) || contains(Name, `cloudformation`)].Name' --output json`
   *Check for foundational IaC state storage.*

6. `aws dynamodb list-tables --query 'TableNames[?contains(@, `terraform`) || contains(@, `state`)]' --output json`
   *Check for foundational IaC state locking.*

7. `aws ec2 describe-security-groups --output json`
   *Provide full security group data to check for exposed sensitive ports.*

8. `aws iam list-entities-for-policy --policy-arn arn:aws:iam::aws:policy/AdministratorAccess --output json`
   *CRITICAL: Check for any users or non-standard roles with AdministratorAccess.*

## Latest Results

FAIL Immediate failure due to critical security violations: CRITICAL: IAM Users have AdministratorAccess: Terraform, change_template_approver. Use roles instead.
- CRITICAL: Non-standard roles have AdministratorAccess: stacksets-exec-d5e511141f10f5aa9846491550c31da6.

---
*Generated 2025-10-13 12:35 UTC*