# KSI-AFR-02: Set security goals for the cloud service offering based on FedRAMP 20x Phase Two Key Security Indicators (KSIs - you are here), develop automated validation of status and progress to the greatest extent possible, and persistently address all related requirements and recommendations.

## Overview

**Category:** Other
**Status:** PASS
**Last Check:** 2025-11-24 12:24

**What it validates:** Set security goals for the cloud service offering based on FedRAMP 20x Phase Two Key Security Indicators (KSIs - you are here), develop automated validation of status and progress to the greatest extent possible, and persistently address all related requirements and recommendations.

**Why it matters:** Validates the existence of the Phase 2 KSI Compliance Tracker.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path authorization_by_fedramp/phase_2_ksi_compliance_tracker.html`
   *Check for KSI Compliance Tracker.*

## Latest Results

PASS Excellent 5/5 (100%): PASS [Documentation] KSI Compliance Tracker found in CodeCommit.
- PASS [Quality] Document appears substantial (195834 bytes).

---
*Generated 2025-11-24 12:34 UTC*