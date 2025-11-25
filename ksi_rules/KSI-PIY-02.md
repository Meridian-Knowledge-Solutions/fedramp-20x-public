# KSI-PIY-02: Document the security objectives and requirements for each information resource or set of information resources.

## Overview

**Category:** Policy and Inventory
**Status:** PASS
**Last Check:** 2025-11-25 04:24

**What it validates:** Document the security objectives and requirements for each information resource or set of information resources.

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

PASS Strong 13/16 (81%): PASS Security governance repository configured.
- PASS System-level security overview documented.
- PASS Component security documentation: 4 components documented (Api Gateway, Application Load Balancer, Ec2 Instances...).
- PASS PR approval workflow capability detected.
- PASS Active documentation management indicated by recent repository activity.
- PASS Main/Master branch configured.

---
*Generated 2025-11-25 04:34 UTC*