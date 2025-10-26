# KSI-PIY-02: Document the security objectives and requirements for EACH information resource

## Overview

**Category:** Policy and Inventory
**Status:** PASS
**Last Check:** 2025-10-26 18:56

**What it validates:** Document the security objectives and requirements for EACH information resource

**Why it matters:** RFC-0014 Phase Two: Validates per-component security documentation in version-controlled CodeCommit. 'Each resource' means system components (frontend, API, database), NOT per-AWS-service-type.

## Validation Method

1. `aws codecommit get-repository --repository-name security-governance --output json`
   *Verify security-governance repository exists*

2. `aws codecommit get-folder --repository-name security-governance --folder-path policies/security-objectives/ --output json`
   *List per-component security documentation (expected: 3-5 system components)*

3. `aws codecommit list-approval-rule-templates --output json`
   *Validate PR approval workflow configured*

4. `aws codecommit get-differences --repository-name security-governance --after-commit-specifier refs/heads/main --output json`
   *Check recent documentation updates*

5. `aws codecommit get-branch --repository-name security-governance --branch-name main --output json`
   *Validate main branch configuration*

## Latest Results

PASS Good per-component documentation (11/16): PASS Security governance repository configured
- PASS Component security documentation: 4 components documented
- PASS System-level security overview documented
- PASS Components covered: Database Security, Web Application Security
- PASS PR approval workflow enforced
- PASS Active documentation management: 11 recent changes
- PASS Main branch configured

---
*Generated 2025-10-26 18:56 UTC*