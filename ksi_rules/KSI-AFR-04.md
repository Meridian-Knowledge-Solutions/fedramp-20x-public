# KSI-AFR-04: Document the vulnerability detection and vulnerability response methodology used within the cloud service offering in alignment with the FedRAMP Vulnerability Detection and Response (VDR) standard and persistently address all related requirements and recommendations.

## Overview

**Category:** Other
**Status:** PASS
**Last Check:** 2025-11-25 04:24

**What it validates:** Document the vulnerability detection and vulnerability response methodology used within the cloud service offering in alignment with the FedRAMP Vulnerability Detection and Response (VDR) standard and persistently address all related requirements and recommendations.

**Why it matters:** Hybrid check: Validates active Inspector scanning (Technical) AND the existence of the compliance tracker (Governance).

## Validation Method

1. `aws inspector2 get-configuration --output json`
   *Check Inspector configuration.*

2. `aws codecommit get-file --repository-name security-governance --file-path authorization_by_fedramp/phase_2_ksi_compliance_tracker.html`
   *Check for Compliance Tracker.*

## Latest Results

PASS Excellent 10/10 (100%): PASS [Technical] Inspector active. Mode: EC2_HYBRID (Status: SUCCESS).
- PASS [Documentation] Vulnerability Policy/Tracker found in CodeCommit.
- PASS [Quality] Document appears substantial (195834 bytes).

---
*Generated 2025-11-25 04:34 UTC*