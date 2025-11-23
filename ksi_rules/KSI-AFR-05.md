# KSI-AFR-05: Verify SCN procedures are documented and active change tracking is visible via GitHub Issues.

## Overview

**Category:** Other
**Status:** FAIL
**Last Check:** 2025-11-23 06:18

**What it validates:** Verify SCN procedures are documented and active change tracking is visible via GitHub Issues.

**Why it matters:** Validates existence of the SCN Procedures markdown (Governance) and queries GitHub Issues to prove the automation is actively creating tracking tickets (Evidence).

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path procedures/scn_procedures.md --output json`
   *Governance: Validates SCN procedures documentation exists.*

2. `gh issue list --repo Meridian-Knowledge-Solutions/fedramp-20x-submission-final --state all --label scn --limit 5 --json number,title,state,labels,createdAt --jq '.' 2>/dev/null || echo '[]'`
   *Observability: Checks for existence of SCN tracking issues (Adaptive/Transformative) as evidence of active workflow.*

## Latest Results

FAIL Insufficient 5/10 (50%): PASS [Governance] SCN Procedures found (3413 bytes).
- WARNING [Evidence] No issues found in the repository (CLI command returned 0 items).

---
*Generated 2025-11-23 06:28 UTC*