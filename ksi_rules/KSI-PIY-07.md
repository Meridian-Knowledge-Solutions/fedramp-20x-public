# KSI-PIY-07: Document risk management decisions for software supply chain security

## Overview

**Category:** Policy and Inventory
**Status:** FAIL
**Last Check:** 2025-10-09 20:38

**What it validates:** Document risk management decisions for software supply chain security

**Why it matters:** Validates supply chain risk management decisions in version-controlled repository with approval audit trail and vendor assessments.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path policies/supply-chain-risk-management.md --output json`
   *Retrieve supply chain risk management policy*

2. `aws codecommit get-folder --repository-name security-governance --folder-path policies/TPR/ --output json`
   *List vendor assessments and third-party documentation*

3. `aws codecommit get-differences --repository-name security-governance --after-commit-specifier refs/heads/main --output json`
   *Audit trail of supply chain risk decisions*

4. `aws codecommit list-pull-requests --repository-name security-governance --pull-request-status CLOSED --max-results 20 --output json`
   *Verify approval workflow for risk management decisions*

## Latest Results

- FAIL No automated supply chain risk management (1/11): WARNING Legacy supply chain documentation - migrate to CodeCommit

---
*Generated 2025-10-09 20:38 UTC*