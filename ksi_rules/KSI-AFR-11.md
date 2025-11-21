# KSI-AFR-11: Ensure that cryptographic modules used to protect potentially sensitive federal customer data are selected and used in alignment with the FedRAMP 20x Using Cryptographic Modules (UCM) policy and persistently address all related requirements and recommendations.

## Overview

**Category:** Other
**Status:** FAIL
**Last Check:** 2025-11-21 06:24

**What it validates:** Ensure that cryptographic modules used to protect potentially sensitive federal customer data are selected and used in alignment with the FedRAMP 20x Using Cryptographic Modules (UCM) policy and persistently address all related requirements and recommendations.

**Why it matters:** Hybrid check: Validates KMS usage (Technical) AND the UCM policy document (Governance).

## Validation Method

1. `aws KMS list-keys --output json`
   *Check KMS keys.*

2. `aws codecommit get-file --repository-name security-governance --file-path cryptography/UCM.md`
   *Check for UCM Policy.*

## Latest Results

FAIL Insufficient 5/10 (50%): FAIL [Technical] Encryption check failed: FAIL Insufficient 0/20 (0%): No detailed findings
- PASS [Documentation] UCM Policy found in CodeCommit.
- PASS [Quality] Document appears substantial (10428 bytes).

---
*Generated 2025-11-21 06:36 UTC*