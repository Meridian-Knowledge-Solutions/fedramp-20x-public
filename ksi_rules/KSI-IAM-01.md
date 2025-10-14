# KSI-IAM-01: Enforce phishing-resistant MFA for all user authentication

## Overview

**Category:** Identity and Access Management
**Status:** FAIL
**Last Check:** 2025-10-14 00:47

**What it validates:** Enforce phishing-resistant MFA for all user authentication

**Why it matters:** Validates MFA via Identity Center and federation, while accurately identifying human IAM users by checking for console passwords before verifying their MFA status.

## Validation Method

1. `aws iam list-users --output json`
   *Get all traditional IAM users to analyze.*

2. `aws sso-admin list-instances --output json`
   *Verify that AWS Identity Center is the primary identity platform.*

3. `aws identitystore list-users --identity-store-id d-9067ccc0ff --output json`
   *Get Identity Center users to confirm federation.*

4. `for user in $(aws iam list-users --query 'Users[].UserName' --output text); do aws iam get-login-profile --user-name "$user" --output json; done`
   *NEW: Loop through each IAM user to check for a console password. Success indicates a human user.*

5. `for user in $(aws iam list-users --query 'Users[].UserName' --output text); do echo "User: $user"; aws iam list-mfa-devices --user-name "$user" --output json; done`
   *Loop through each IAM user to check for attached MFA devices.*

## Latest Results

- Exception during evaluation: 'dict' object has no attribute 'splitlines'

---
*Generated 2025-10-14 00:47 UTC*