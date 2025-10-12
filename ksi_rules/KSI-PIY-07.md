# KSI-PIY-07: Document risk management decisions for software supply chain security

## Overview

**Category:** Policy and Inventory
**Status:** FAIL
**Last Check:** 2025-10-12 03:08

**What it validates:** Document risk management decisions for software supply chain security

**Why it matters:** Validates the supply chain risk policy's content, its maintenance history, and the existence of a formal approval workflow.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path policies/supply-chain-risk-management.md --output json`
   *Retrieve the supply chain risk management policy to analyze its content.*

2. `aws codecommit get-differences --repository-name security-governance --after-commit-specifier refs/heads/main --output json`
   *Check the commit history for an audit trail of policy updates.*

3. `aws codecommit list-approval-rule-templates-for-repository --repository-name security-governance --output json`
   *Verify that a formal approval process is configured for the repository.*

## Latest Results

FAIL Insufficient documentation for supply chain risk management (20%): FAIL [Policy] The supply chain risk management policy document is missing or insufficient.
- WARNING [Approval] No formal approval rule templates were found for the repository.
- PASS [Audit Trail] The policy is actively maintained, with evidence of 1 recent update(s).

---
*Generated 2025-10-12 03:08 UTC*