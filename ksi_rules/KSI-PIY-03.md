# KSI-PIY-03: Maintain a vulnerability disclosure program

## Overview

**Category:** Policy and Inventory
**Status:** FAIL
**Last Check:** 2025-10-29 01:18

**What it validates:** Maintain a vulnerability disclosure program

**Why it matters:** Validates vulnerability disclosure program through CodeCommit policy repository with submission process, response procedures, and maintenance tracking

## Validation Method

1. `aws codecommit list-repositories --output json`
   *Verify security-governance repository exists*

2. `aws codecommit get-file --repository-name security-governance --file-path policies/vulnerability-disclosure-policy.md --output json`
   *Retrieve vulnerability disclosure policy from CodeCommit*

3. `aws codecommit get-differences --repository-name security-governance --after-commit-specifier HEAD --output json`
   *Check VDP maintenance activity through commit history*

4. `aws codecommit get-folder --repository-name security-governance --folder-path policies --output json`
   *List all policy documents for supporting VDP documentation*

## Latest Results

- FAIL No vulnerability disclosure program detected (1/14): PASS VDP maintenance activity: 1 updates

---
*Generated 2025-10-29 01:18 UTC*