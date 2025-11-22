# KSI-AFR-04: Document the vulnerability detection and vulnerability response methodology used within the cloud service offering in alignment with the FedRAMP Vulnerability Detection and Response (VDR) standard and persistently address all related requirements and recommendations.

## Overview

**Category:** Other
**Status:** FAIL
**Last Check:** 2025-11-22 02:45

**What it validates:** Document the vulnerability detection and vulnerability response methodology used within the cloud service offering in alignment with the FedRAMP Vulnerability Detection and Response (VDR) standard and persistently address all related requirements and recommendations.

**Why it matters:** Hybrid check: Validates active Inspector scanning (Technical) AND the existence of the compliance tracker (Governance).

## Validation Method

1. `aws inspector2 get-configuration --output json`
   *Check Inspector configuration.*

2. `aws codecommit get-file --repository-name security-governance --file-path authorization_by_fedramp/phase_2_ksi_compliance_tracker.html`
   *Check for Compliance Tracker.*

## Latest Results

FAIL Insufficient 5/10 (50%): FAIL [Technical] Inspector check failed: FAIL Insufficient 4/18 (22%): WARNING Security Hub standards data unavailable.
- PASS Automated vulnerability scanning: Inspector enabled for EC2, ECR.
- PASS Multi-service vulnerability coverage via Inspector (2 services).
- PASS [Documentation] Vulnerability Policy/Tracker found in CodeCommit.
- PASS [Quality] Document appears substantial (195834 bytes).

---
*Generated 2025-11-22 02:58 UTC*