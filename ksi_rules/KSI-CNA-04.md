# KSI-CNA-04: Use immutable infrastructure with strictly defined functionality and privileges

## Overview

**Category:** Cloud Native Architecture
**Status:** PASS
**Last Check:** 2025-10-20 03:24

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

PASS Foundational immutable practices (58%): PASS Least Privilege: AdministratorAccess is properly restricted to AWS-managed infrastructure roles.
- PASS Network Security: No sensitive ports are exposed to the internet.
- PASS Serverless Adoption: 18 Lambda functions are in use (inherently immutable).
- WARNING EC2 Standardization: No Launch Templates found for 6 running instance(s).
- WARNING EC2 Immutable Scaling: No Auto Scaling Groups found for 6 running instance(s).
- FAIL EC2 IaC Management: None of the 6 running instance(s) have IaC tags.

---
*Generated 2025-10-20 03:24 UTC*