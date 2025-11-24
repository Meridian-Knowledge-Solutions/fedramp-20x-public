# KSI-AFR-09: Persistently validate security posture using automated pipelines.

## Overview

**Category:** Other
**Status:** FAIL
**Last Check:** 2025-11-24 12:24

**What it validates:** Persistently validate security posture using automated pipelines.

**Why it matters:** Hybrid check: Validates the architecture diagram AND the execution status of the Master Validator pipeline.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path authorization_by_fedramp/fedramp-phase2-validation-architecture.mmd --output json`
   *Check for Validation Architecture Diagram in the correct folder.*

2. `gh run list --workflow "FedRAMP 20x CLI Validation Pipeline + Phase 2 Master Validator" --limit 1 --json name,status,conclusion,databaseId,updatedAt`
   *Check for the latest successful run of the Master Validator pipeline.*

## Latest Results

FAIL Insufficient 5/10 (50%): PASS [Documentation] Validation Architecture Diagram found in CodeCommit.
- PASS [Quality] Document appears substantial (7420 bytes).
- WARNING [Technical] GitHub CLI command failed or missing (gh run list).

---
*Generated 2025-11-24 12:34 UTC*