# KSI-AFR-05: Determine how significant changes will be tracked and how all necessary parties will be notified in alignment with the FedRAMP Significant Change Notifications (SCN) standard and persistently address all related requirements and recommendations.

## Overview

**Category:** Other
**Status:** FAIL
**Last Check:** 2025-11-21 06:24

**What it validates:** Determine how significant changes will be tracked and how all necessary parties will be notified in alignment with the FedRAMP Significant Change Notifications (SCN) standard and persistently address all related requirements and recommendations.

**Why it matters:** Hybrid check: Validates Terraform plans in S3 (Technical) AND the compliance tracker (Governance).

## Validation Method

1. `aws s3 ls s3://mks-states/plans/ --recursive`
   *Check for Terraform plans.*

2. `aws codecommit get-file --repository-name security-governance --file-path authorization_by_fedramp/phase_2_ksi_compliance_tracker.html`
   *Check for Compliance Tracker.*

## Latest Results

FAIL Insufficient 5/10 (50%): FAIL [Technical] Terraform plan check failed: Error in wrapped function evaluate_KSI_CMT_05: 'str' object has no attribute 'get'
- PASS [Documentation] Change Management Tracker found in CodeCommit.
- PASS [Quality] Document appears substantial (195834 bytes).

---
*Generated 2025-11-21 06:36 UTC*