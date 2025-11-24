# KSI-PIY-07: Document risk management decisions for software supply chain security.

## Overview

**Category:** Policy and Inventory
**Status:** PASS
<<<<<<< Updated upstream
**Last Check:** 2025-11-24 06:20
=======
**Last Check:** 2025-11-24 06:44
>>>>>>> Stashed changes

**What it validates:** Document risk management decisions for software supply chain security.

**Why it matters:** Validates the supply chain risk policy's content, its maintenance history, and the existence of a formal approval workflow.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path policies/supply-chain-risk-management.md --output json`
   *Retrieve the supply chain risk management policy to analyze its content.*

2. `aws codecommit get-differences --repository-name security-governance --after-commit-specifier refs/heads/main --output json`
   *Check the commit history for an audit trail of policy updates.*

3. `aws codecommit list-approval-rule-templates --output json`
   *Verify that a formal approval process is configured for the repository.*

## Latest Results

PASS Excellent 10/10 (100%): PASS [Policy] Supply chain risk management policy document exists and is substantial (3847 bytes).
- PASS [Approval] Formal approval process capability detected (1 approval rule template(s)).
- PASS [Audit Trail] Policy appears actively maintained (1 recent update(s) detected).

---
<<<<<<< Updated upstream
*Generated 2025-11-24 06:31 UTC*
=======
*Generated 2025-11-24 06:55 UTC*
>>>>>>> Stashed changes
