# KSI-AFR-05: Determine how significant changes will be tracked and how all necessary parties will be notified in alignment with the FedRAMP Significant Change Notifications (SCN) standard and persistently address all related requirements and recommendations.

## Overview

**Category:** Other
**Status:** FAIL
**Last Check:** 2025-11-22 02:45

**What it validates:** Determine how significant changes will be tracked and how all necessary parties will be notified in alignment with the FedRAMP Significant Change Notifications (SCN) standard and persistently address all related requirements and recommendations.

**Why it matters:** Multi-layered validation: Technical tracking (Terraform plans in S3), Governance documentation (compliance tracker + SCN procedures), Operational evidence (scn_history.jsonl with change records), Active monitoring (GitHub issues for adaptive changes).

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path procedures/scn_procedures.md --output json`
   *Governance: Validates SCN procedures documentation exists with notification workflows.*

2. `aws s3 ls s3://mks-states/plans/ --recursive --output json`
   *Technical: Validates Terraform plans exist in S3 (infrastructure change tracking).*

3. `aws codecommit get-file --repository-name fedramp-20x-submission-final --file-path scn_automation/scn_history.jsonl --output json`
   *Evidence: Validates historical SCN tracking file exists with change records over time (FRR-SCN-04, FRR-SCN-05).*

4. `gh issue list --repo Meridian-Knowledge-Solutions/fedramp-20x-submission-final --state all --label adaptive,scn --limit 100 --json number,title,state,createdAt,closedAt,labels --jq '.' 2>/dev/null || echo '{"error": "gh cli not available or no issues found"}'`
   *Observability: Lists SCN/adaptive change issues (proves automation actively tracking and notifying changes).*

5. `aws codecommit get-file --repository-name security-governance --file-path authorization_by_fedramp/phase_2_ksi_compliance_tracker.html --output json`
   *Governance: Validates Phase 2 compliance tracker exists.*

## Latest Results

FAIL Insufficient 0/10 (0%): FAIL [SCN Procedures] SCN procedures documentation not found in security-governance repo
- WARNING [Terraform Plans] Could not verify Terraform plans in S3
- WARNING [Historical Tracking] scn_history.jsonl not found (may be new deployment)
- WARNING [GitHub Issues] No output from gh command (CLI may not be configured)
- FAIL [Compliance Tracker] Phase 2 compliance tracker not found

---
*Generated 2025-11-22 02:58 UTC*