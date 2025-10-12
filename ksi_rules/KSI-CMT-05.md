# KSI-CMT-05: Evaluate risk and potential impact of any change (Hybrid Validation)

## Overview

**Category:** Change Management
**Status:** FAIL
**Last Check:** 2025-10-12 03:08

**What it validates:** Evaluate risk and potential impact of any change (Hybrid Validation)

**Why it matters:** Performs a hybrid check: 1) A live call to AWS CodeCommit to verify the risk assessment document exists. 2) Reads the SCN workflow artifact to verify risk is being assessed.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --commit-specifier main --file-path security-governance/procedures/change-risk-assessment.md`
   *Live check for the risk assessment procedure in CodeCommit.*

2. `test -f evidence_v2/KSI-CMT-05/ksi_compliance_report.json && cat evidence_v2/KSI-CMT-05/ksi_compliance_report.json || echo '{"error": "Compliance report artifact not found"}'`
   *Reads the SCN artifact to find evidence of adherence (commit keyword analysis).*

## Latest Results

FAIL Phase 2 Non-Compliant (0%): Hybrid check failed. Findings: FAIL [Live Check] Risk assessment procedure not found in AWS CodeCommit.
- FAIL [Artifact] SCN compliance report artifact not found or is invalid.

---
*Generated 2025-10-12 03:08 UTC*