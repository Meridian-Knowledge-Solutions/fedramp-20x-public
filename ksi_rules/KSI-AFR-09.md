# KSI-AFR-09: Persistently validate, assess, and report on the effectiveness and status of security decisions and policies that are implemented within the cloud service offering in alignment with the FedRAMP 20x Persistent Validation and Assessment (PVA) standard, and persistently address all related requirements and recommendations.

## Overview

**Category:** Other
**Status:** FAIL
**Last Check:** 2025-11-22 01:14

**What it validates:** Persistently validate, assess, and report on the effectiveness and status of security decisions and policies that are implemented within the cloud service offering in alignment with the FedRAMP 20x Persistent Validation and Assessment (PVA) standard, and persistently address all related requirements and recommendations.

**Why it matters:** Hybrid check: Validates the validation architecture diagram AND the existence of the scheduled EventBridge trigger.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path architecture/fedramp-phase2-validation-architecture.mmd`
   *Check for Validation Architecture Diagram.*

2. `aws events list-rules --name-prefix fedramp-validation --output json`
   *Check for automated validation schedule rules.*

## Latest Results

FAIL Insufficient 0/10 (0%): FAIL [Documentation] Validation Architecture Diagram NOT found in the expected CodeCommit path.
- WARNING [Technical] EventBridge validation schedule not explicitly found.

---
*Generated 2025-11-22 01:27 UTC*