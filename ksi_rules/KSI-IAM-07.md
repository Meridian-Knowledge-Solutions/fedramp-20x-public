# KSI-IAM-07: Securely manage the lifecycle and privileges of all accounts, roles, and groups, using automation.

## Overview

**Category:** Identity and Access Management
**Status:** PASS
**Last Check:** 2025-11-22 02:45

**What it validates:** Securely manage the lifecycle and privileges of all accounts, roles, and groups, using automation.

**Why it matters:** Validates comprehensive identity lifecycle management, including role usage, policy activity, and centralized management via AWS Identity Center.

## Validation Method

1. `aws iam list-roles --output json`
   *Check IAM roles for consistent identity management.*

2. `aws iam list-users --output json`
   *Validate IAM users and lifecycle management.*

3. `aws iam list-policies --scope Local --output json`
   *Check custom IAM policies for consistent identity governance and activity.*

4. `aws sso-admin list-instances --output json`
   *Check for AWS Identity Center (SSO) usage for central management.*

## Latest Results

PASS Strong 8/10 (80%): PASS Service Oriented Architecture: Excellent - 97 roles with 0 IAM users indicates strong role-based access.
- PASS Active Lifecycle Management: 17/21 custom policies updated in the last 90 days.
- PASS Advanced Identity Management: AWS Identity Center is active (1 instance(s) found). Enables central privilege/access reviews.

---
*Generated 2025-11-22 02:58 UTC*