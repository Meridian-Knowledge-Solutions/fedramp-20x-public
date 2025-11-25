# KSI-IAM-02: Use secure passwordless methods for user authentication and authorization when feasible, otherwise enforce strong passwords with MFA.

## Overview

**Category:** Identity and Access Management
**Status:** PASS
**Last Check:** 2025-11-25 06:24

**What it validates:** Use secure passwordless methods for user authentication and authorization when feasible, otherwise enforce strong passwords with MFA.

**Why it matters:** Validates comprehensive identity federation from basic SAML to enterprise-grade SSO and centralized identity management

## Validation Method

1. `aws iam list-saml-providers --output json`
   *Check SAML identity providers for federated authentication*

2. `aws iam list-virtual-mfa-devices --output json`
   *Validate virtual MFA devices in federated authentication*

3. `aws iam get-account-password-policy --output json || echo '{"PasswordPolicy": "NotConfigured"}'`
   *Check password policy for federated identity fallback requirements*

4. `aws sts get-caller-identity --output json`
   *Validate federated identity assumption and role-based access*

## Latest Results

PASS Strong 5/6 (83%): PASS 1 SAML providers configured (passwordless authentication)
- PASS Using temporary credentials (assumed role - passwordless method)
- PASS Centralized MFA via SAML/IdP assumed (IAM MFA devices not strictly required).

---
*Generated 2025-11-25 06:34 UTC*