# KSI-PIY-02: Document the security objectives and requirements for EACH information resource

## Overview

**Category:** Policy and Inventory
**Status:** FAIL
**Last Check:** 2025-10-09 20:38

**What it validates:** Document the security objectives and requirements for EACH information resource

**Why it matters:** RFC-0014 Phase Two: Validates per-resource security documentation in version-controlled CodeCommit repository with PR approval workflows. Changed from general policies to granular per-resource documentation.

## Validation Method

1. `aws codecommit get-repository --repository-name security-governance --output json`
   *Verify security-governance repository exists*

2. `aws codecommit get-folder --repository-name security-governance --folder-path policies/PIY/resources/ --output json`
   *List per-resource security documentation (EC2, RDS, S3, Lambda, etc.)*

3. `aws codecommit list-approval-rule-templates --output json`
   *Validate PR approval templates configured*

4. `aws codecommit get-differences --repository-name security-governance --after-commit-specifier refs/heads/main --output json`
   *Check recent per-resource documentation updates*

5. `aws codecommit get-branch --repository-name security-governance --branch-name main --output json`
   *Validate main branch configuration*

## Latest Results

- FAIL Insufficient per-resource security documentation (1/14): WARNING Legacy evidence found (2 PDFs) - migrate to per-resource CodeCommit documentation

---
*Generated 2025-10-09 20:38 UTC*