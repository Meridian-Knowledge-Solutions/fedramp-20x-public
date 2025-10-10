# KSI-PIY-07: Document risk management decisions for software supply chain security

## Overview

**Category:** Policy and Inventory
**Status:** PASS
**Last Check:** 2025-10-10 03:07

**What it validates:** Document risk management decisions for software supply chain security

**Why it matters:** Validates supply chain risk management decisions with vendor assessment procedures and audit trail.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path policies/supply-chain-risk-management.md --output json`
   *Retrieve supply chain risk management policy*

2. `aws codecommit get-folder --repository-name security-governance --folder-path policies/ --output json`
   *List vendor assessments and third-party documentation*

3. `aws codecommit get-differences --repository-name security-governance --after-commit-specifier refs/heads/main --output json`
   *Audit trail of supply chain risk decisions*

4. `aws codecommit list-pull-requests --repository-name security-governance --pull-request-status CLOSED --max-results 20 --output json`
   *Verify approval workflow for risk management decisions*

## Latest Results

- WARNING Minimal supply chain documentation (2/12): WARNING Legacy supply chain documentation found - migrate to CodeCommit

---
*Generated 2025-10-10 03:07 UTC*