# KSI-PIY-05: Document methods used to evaluate information resource implementations

## Overview

**Category:** Policy and Inventory
**Status:** PASS
**Last Check:** 2025-10-10 03:07

**What it validates:** Document methods used to evaluate information resource implementations

**Why it matters:** Validates evaluation methodology including assessment procedures and automated tools (AWS CLI, Config, Security Hub).

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path procedures/evaluation-methodology.md --output json`
   *Retrieve evaluation methodology document*

2. `aws codecommit get-folder --repository-name security-governance --folder-path procedures/ --output json`
   *List evaluation and assessment procedures*

3. `aws codecommit get-differences --repository-name security-governance --after-commit-specifier refs/heads/main --output json`
   *Check methodology updates*

## Latest Results

- WARNING Minimal methodology present (2/12): WARNING Legacy evaluation documentation found - migrate to CodeCommit

---
*Generated 2025-10-10 03:07 UTC*