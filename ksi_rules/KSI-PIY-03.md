# KSI-PIY-03: Maintain a vulnerability disclosure program

## Overview

**Category:** Policy and Inventory
**Status:** PASS
**Last Check:** 2025-11-19 16:15

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

PASS Excellent 14/14 (100%): PASS Vulnerability disclosure policy document found and appears valid.
- PASS Submission process appears documented within the policy.
- PASS Response procedures/timelines appear defined within the policy.
- PASS Public security contact information appears provided within the policy.
- PASS VDP maintenance activity: 1 recent update(s) to policy detected.

---
*Generated 2025-11-19 16:15 UTC*