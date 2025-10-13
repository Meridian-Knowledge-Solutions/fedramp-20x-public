# KSI-PIY-03: Maintain a vulnerability disclosure program

## Overview

**Category:** Policy and Inventory
**Status:** FAIL
**Last Check:** 2025-10-13 12:35

**What it validates:** Maintain a vulnerability disclosure program

**Why it matters:** Validates vulnerability disclosure program with submission procedures, response timelines, and public contact information.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path policies/vulnerability-disclosure-policy.md --output json`
   *Retrieve vulnerability disclosure policy document*

2. `aws codecommit get-folder --repository-name security-governance --folder-path policies/ --output json`
   *List supporting VDP documentation*

3. `aws codecommit get-differences --repository-name security-governance --after-commit-specifier refs/heads/main --output json`
   *Check VDP maintenance and updates*

## Latest Results

- FAIL No vulnerability disclosure program detected (1/14): PASS VDP maintenance activity: 1 updates

---
*Generated 2025-10-13 12:35 UTC*