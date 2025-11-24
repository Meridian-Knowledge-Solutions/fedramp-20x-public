# KSI-CNA-04: Use immutable infrastructure with strictly defined functionality and privileges by default.

## Overview

**Category:** Cloud Native Architecture
**Status:** PASS
**Last Check:** 2025-11-24 04:30

**What it validates:** Use immutable infrastructure with strictly defined functionality and privileges by default.

**Why it matters:** Validates a hybrid infrastructure model by checking for: 1) Serverless adoption (Lambda). 2) IaC workflow (S3 state/plans). 3) Automated controls (CMT-03 artifacts). 4) Least privilege (IAM). 5) Network security (SGs).

## Validation Method

1. `aws s3 ls s3://mks-states/ --recursive`
   *Check S3 for Terraform state and plan files as evidence of an immutable IaC workflow.*

2. `aws lambda list-functions --output json`
   *Validate adoption of inherently immutable serverless functions.*

3. `aws ec2 describe-security-groups --output json`
   *Provide full security group data to check for exposed sensitive ports.*

4. `aws iam list-entities-for-policy --policy-arn arn:aws:iam::aws:policy/AdministratorAccess --output json`
   *CRITICAL: Check for any users or non-standard roles with AdministratorAccess.*

5. `aws iam list-roles --output json`
   *Provide full role details (Path, Description) to validate if admin roles are AWS-managed.*

## Latest Results

PASS Excellent 9/10 (90%): PASS [Least Privilege] AdministratorAccess is properly restricted to AWS-managed infrastructure roles.
- PASS [Network Security] No sensitive ports (SSH, RDP, DBs) are exposed to the internet.
- PASS [IaC Controls] IaC Scan Artifact ('checkov_scan_summary.json') found.
- PASS [IaC Controls] Testing Proof Artifact ('automated_testing_proof.json') found.
- WARNING [Foundational IaC] S3 bucket data (s3://mks-states/) unavailable.
- PASS [Serverless Adoption] 20 Lambda functions are in use (inherently immutable).

---
*Generated 2025-11-24 04:38 UTC*