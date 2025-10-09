# KSI-PIY-03: Maintain a vulnerability disclosure program

## Overview

**Category:** Policy and Inventory
**Status:** FAIL
**Last Check:** 2025-10-09 20:38

**What it validates:** Maintain a vulnerability disclosure program

**Why it matters:** CORRECTED: Validates vulnerability disclosure program (NOT baselines) in version-controlled repository with public accessibility and response procedures.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path policies/vulnerability-disclosure-policy.md --output json`
   *Retrieve vulnerability disclosure policy document*

2. `aws codecommit get-folder --repository-name security-governance --folder-path policies/vulnerability-disclosure/ --output json`
   *List VDP supporting documentation (submission process, response procedures)*

3. `aws codecommit get-differences --repository-name security-governance --after-commit-specifier refs/heads/main --output json`
   *Check VDP maintenance and updates*

4. `aws codecommit get-commit-history --repository-name security-governance --output json`
   *Audit trail of VDP policy changes*

## Latest Results

- FAIL No vulnerability disclosure program detected (1/14): WARNING Legacy VDP documentation - migrate to CodeCommit

---
*Generated 2025-10-09 20:38 UTC*