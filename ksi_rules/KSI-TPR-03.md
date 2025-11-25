# KSI-TPR-03: Identify and prioritize mitigation of potential supply chain risks.

## Overview

**Category:** Third-Party Information Resources
**Status:** PASS
<<<<<<< Updated upstream
**Last Check:** 2025-11-25 12:25
=======
**Last Check:** 2025-11-25 12:49
>>>>>>> Stashed changes

**What it validates:** Identify and prioritize mitigation of potential supply chain risks.

**Why it matters:** Validates the supply chain risk management policy's existence, its maintenance history, and the existence of a formal approval workflow.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path policies/supply-chain-risk-management.md`
   *Retrieve the supply chain risk management policy from CodeCommit to verify its existence and size.*

2. `aws codecommit list-approval-rule-templates --output json`
   *Validate that a formal approval rule process is configured for the repository.*

3. `aws codecommit get-differences --repository-name security-governance --after-commit-specifier refs/heads/main --output json`
   *Check the commit history for an audit trail of recent policy updates.*

## Latest Results

PASS Excellent 10/10 (100%): PASS [Policy] A comprehensive supply chain risk management policy is documented (3847 bytes).
- PASS [Approval] Formal approval process capability detected (1 approval rule template(s)).
- PASS [Audit Trail] Policy appears actively maintained (1 recent update(s) detected).

---
<<<<<<< Updated upstream
*Generated 2025-11-25 12:35 UTC*
=======
*Generated 2025-11-25 12:59 UTC*
>>>>>>> Stashed changes
