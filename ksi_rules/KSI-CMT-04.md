# KSI-CMT-04: Document and consistently follow change management

## Overview

**Category:** Change Management
**Status:** PASS
**Last Check:** 2025-10-27 18:57

**What it validates:** Document and consistently follow change management

**Why it matters:** Verifies that a change management procedure is documented and that the process is being followed by checking for stored Terraform plan files in S3.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path procedures/change-management-procedure.md`
   *Check for the existence of the change management procedure document.*

2. `aws s3 ls s3://mks-states/plans/ --recursive`
   *Check S3 for stored Terraform plans as evidence that the change process is followed.*

## Latest Results

PASS Excellent change management process (100%): PASS [Documentation] Comprehensive change management procedure found (8898 bytes).
- PASS [Evidence] Found 2 recent Terraform plan(s) in S3, proving the change process is followed.

---
*Generated 2025-10-27 18:57 UTC*