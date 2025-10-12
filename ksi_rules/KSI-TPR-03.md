# KSI-TPR-03: Identify and prioritize mitigation of potential supply chain risks

## Overview

**Category:** Third-Party Information Resources
**Status:** FAIL
**Last Check:** 2025-10-12 03:08

**What it validates:** Identify and prioritize mitigation of potential supply chain risks

**Why it matters:** Validates the supply chain risk management policy in CodeCommit, checks for an approval workflow, and verifies migration from legacy SSM.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path policies/supply-chain-risk-management.md`
   *Retrieve the supply chain risk management policy from CodeCommit.*

2. `aws codecommit list-approval-rule-templates-for-repository --repository-name security-governance`
   *Validate that an approval rule process is configured for the repository.*

## Latest Results

- FAIL Insufficient supply chain risk management (4/13): PASS Supply chain policy documentation in repository

---
*Generated 2025-10-12 03:08 UTC*