# KSI-AFR-05: Verify SCN procedures are documented and active change tracking is visible via GitHub Issues.

## Overview

**Category:** Other
**Status:** FAIL
**Last Check:** 2025-11-25 00:48

**What it validates:** Verify SCN procedures are documented and active change tracking is visible via GitHub Issues.

**Why it matters:** Hybrid check: Validates SCN procedures documentation AND the existence of SCN tracking issues in GitHub.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path procedures/scn_procedures.md --output json`
   *Governance: Validates SCN procedures documentation exists.*

2. `gh issue list --repo Meridian-Knowledge-Solutions/fedramp-20x-submission-final --state all --limit 30 --json number,title,state,labels,createdAt --jq '.' 2>/dev/null || echo '[]'`
   *Observability: Fetches recent open/closed issues to check for SCN tracking activity (Adaptive/Transformative).*

## Latest Results

FAIL Insufficient 5/10 (50%): PASS [Governance] SCN Procedures found (3413 bytes).
- WARNING [Evidence] No issues found in the repository (CLI command returned 0 items).

---
*Generated 2025-11-25 00:59 UTC*