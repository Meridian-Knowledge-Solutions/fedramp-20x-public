# KSI-AFR-09: Persistently validate... (PVA) standard...

## Overview

**Category:** Other
**Status:** FAIL
**Last Check:** 2025-11-23 06:18

**What it validates:** Persistently validate... (PVA) standard...

**Why it matters:** Hybrid check: Validates the validation architecture diagram AND the existence of the scheduled EventBridge trigger.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path authorization_by_fedramp/fedramp-phase2-validation-architecture.mmd --output json`
   *Check for Validation Architecture Diagram in the correct folder.*

2. `aws events list-rules --name-prefix fedramp-validation --output json`
   *Check for automated validation schedule rules.*

## Latest Results

FAIL Insufficient 5/10 (50%): PASS [Documentation] Validation Architecture Diagram found in CodeCommit.
- PASS [Quality] Document appears substantial (7420 bytes).
- WARNING [Technical] GitHub CLI command failed or missing (gh run list).

---
*Generated 2025-11-23 06:28 UTC*