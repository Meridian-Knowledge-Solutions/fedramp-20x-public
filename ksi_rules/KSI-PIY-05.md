# KSI-PIY-05: Document methods used to evaluate information resource implementations.

## Overview

**Category:** Policy and Inventory
**Status:** PASS
**Last Check:** 2025-11-25 08:21

**What it validates:** Document methods used to evaluate information resource implementations.

**Why it matters:** Validates the evaluation methodology document, including assessment procedures and references to automated tools.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path policies/evaluation-methodology.md --output json`
   *Retrieve the correct evaluation methodology document from the 'policies' directory.*

2. `aws codecommit get-folder --repository-name security-governance --folder-path procedures/ --output json`
   *List any supporting evaluation and assessment procedures.*

3. `aws codecommit get-differences --repository-name security-governance --after-commit-specifier refs/heads/main --output json`
   *Check for recent updates to the methodology.*

## Latest Results

PASS Excellent 10/10 (100%): PASS [Documentation] Evaluation methodology document exists and appears substantial (4027 bytes).
- PASS [Content] Document appears to define assessment/validation procedures.
- PASS [Content] Methodology appears to reference automated evaluation tools/methods.
- PASS [Maintenance] Methodology appears actively maintained (1 recent update(s) detected).

---
*Generated 2025-11-25 08:31 UTC*