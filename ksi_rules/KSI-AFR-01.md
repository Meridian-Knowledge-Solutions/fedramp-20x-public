# KSI-AFR-01: Apply the FedRAMP Minimum Assessment Standard (MAS) to identify and document the scope of the cloud service offering to be assessed for FedRAMP authorization and persistently address all related requirements and recommendations.

## Overview

**Category:** Other
**Status:** PASS
**Last Check:** 2025-11-24 12:24

**What it validates:** Apply the FedRAMP Minimum Assessment Standard (MAS) to identify and document the scope of the cloud service offering to be assessed for FedRAMP authorization and persistently address all related requirements and recommendations.

**Why it matters:** Validates scope via existence of the scoped assessment declaration document.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path authorization_by_fedramp/minimum_assessment_scope.html`
   *Check for Minimum Assessment Scope document.*

## Latest Results

PASS Excellent 5/5 (100%): PASS [Documentation] Minimum Assessment Scope found in CodeCommit.
- PASS [Quality] Document appears substantial (139831 bytes).

---
*Generated 2025-11-24 12:34 UTC*