# KSI-CMT-05: Evaluate risk and potential impact of any change (Hybrid Validation)

## Overview

**Category:** Change Management
**Status:** PASS
**Last Check:** 2025-11-03 04:39

**What it validates:** Evaluate risk and potential impact of any change (Hybrid Validation)

**Why it matters:** Performs a hybrid check: 1) A live call to AWS CodeCommit to verify the risk assessment document exists. 2) A live call to S3 to verify Terraform plans are being stored as evidence of impact analysis.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --commit-specifier main --file-path procedures/change-risk-assessment.md`
   *Live check for the risk assessment procedure in CodeCommit.*

2. `aws s3 ls s3://mks-states/plans/ --recursive`
   *Check S3 for stored Terraform plans as evidence of impact assessment.*

## Latest Results

PASS Phase 2 Compliant (100%): Hybrid check passed. Findings: PASS [Documentation] Comprehensive risk procedure found in CodeCommit (12157 bytes).
- PASS [Evidence] Found 2 recent Terraform plan(s) in S3, proving pre-change impact assessment.

---
*Generated 2025-11-03 04:39 UTC*