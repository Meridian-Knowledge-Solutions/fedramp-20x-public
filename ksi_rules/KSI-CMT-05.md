# KSI-CMT-05: Evaluate risk and potential impact of any change (Hybrid Validation)

## Overview

**Category:** Change Management
**Status:** PASS
**Last Check:** 2025-10-14 06:36

**What it validates:** Evaluate risk and potential impact of any change (Hybrid Validation)

**Why it matters:** Performs a hybrid check: 1) A live call to AWS CodeCommit to verify the risk assessment document exists. 2) Reads the SCN workflow artifact to verify risk is being assessed.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --commit-specifier main --file-path procedures/change-risk-assessment.md`
   *Live check for the risk assessment procedure in CodeCommit.*

2. `test -f evidence_v2/KSI-CMT-05/ksi_compliance_report.json && cat evidence_v2/KSI-CMT-05/ksi_compliance_report.json || echo '{"error": "Compliance report artifact not found"}'`
   *Reads the SCN artifact to find evidence of adherence (commit keyword analysis).*

## Latest Results

PASS Phase 2 Compliant (100%): Hybrid check passed. Findings: PASS [Live Check] Comprehensive risk procedure found in CodeCommit (12157 bytes).
- PASS [Artifact] PASS Evidence of risk assessments: 1 commits with risk keywords

---
*Generated 2025-10-14 06:36 UTC*