# KSI-PIY-05: Document methods used to evaluate information resource implementations

## Overview

**Category:** Policy and Inventory
**Status:** FAIL
**Last Check:** 2025-10-09 20:38

**What it validates:** Document methods used to evaluate information resource implementations

**Why it matters:** Validates evaluation methodology and assessment procedures in version-controlled repository (NOT data protection policy).

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path procedures/evaluation-methodology.md --output json`
   *Retrieve evaluation methodology document*

2. `aws codecommit get-folder --repository-name security-governance --folder-path procedures/ --output json`
   *List evaluation and assessment procedures*

3. `aws codecommit get-differences --repository-name security-governance --after-commit-specifier refs/heads/main --output json`
   *Check methodology updates*

4. `aws codecommit get-commit-history --repository-name security-governance --output json`
   *Audit trail of methodology changes*

## Latest Results

- FAIL No evaluation methodology documented (1/14): WARNING Legacy evaluation documentation - migrate to CodeCommit

---
*Generated 2025-10-09 20:38 UTC*