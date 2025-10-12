# KSI-CMT-04: Consistently follow documented change management procedure (Hybrid Validation)

## Overview

**Category:** Change Management
**Status:** FAIL
**Last Check:** 2025-10-12 03:08

**What it validates:** Consistently follow documented change management procedure (Hybrid Validation)

**Why it matters:** Performs a hybrid check: 1) A live call to AWS CodeCommit to verify the procedure document exists. 2) Reads the SCN workflow artifact to verify the procedure is being followed.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --commit-specifier main --file-path security-governance/procedures/change-management-procedure.md`
   *Live check for the change management procedure in CodeCommit.*

2. `test -f evidence_v2/KSI-CMT-04/ksi_compliance_report.json && cat evidence_v2/KSI-CMT-04/ksi_compliance_report.json || echo '{"error": "Compliance report artifact not found"}'`
   *Reads the SCN artifact to find evidence of adherence (commit keyword analysis).*

## Latest Results

FAIL Phase 2 Non-Compliant (0%): Hybrid check failed. Findings: FAIL [Live Check] Change management procedure not found in AWS CodeCommit.
- FAIL [Artifact] SCN compliance report artifact not found or is invalid.

---
*Generated 2025-10-12 03:08 UTC*