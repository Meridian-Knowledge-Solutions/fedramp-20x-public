# KSI-IAM-01: Enforce phishing-resistant MFA for all user authentication

## Overview

**Category:** Identity and Access Management
**Status:** FAIL
**Last Check:** 2025-10-12 03:08

**What it validates:** Enforce phishing-resistant MFA for all user authentication

**Why it matters:** Validates MFA enforcement via Identity Center and federation, while also checking for and verifying MFA on any remaining traditional IAM users.

## Validation Method

1. `aws iam list-users --output json`
   *Get all traditional IAM users to analyze.*

2. `aws sso-admin list-instances --output json`
   *Verify that AWS Identity Center is the primary identity platform.*

3. `aws identitystore list-users --identity-store-id d-9067ccc0ff --output json`
   *Get Identity Center users to confirm federation.*

4. `for user in $(aws iam list-users --query 'Users[].UserName' --output text); do echo "User: $user"; aws iam list-mfa-devices --user-name "$user" --output json; done`
   *Loop through each IAM user to check for attached MFA devices.*

## Latest Results

- Exception during evaluation: 'str' object has no attribute 'get'

---
*Generated 2025-10-12 03:08 UTC*