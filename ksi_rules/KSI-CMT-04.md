# KSI-CMT-04: Document and consistently follow change management

## Overview

**Category:** Change Management
**Status:** PASS
**Last Check:** 2025-11-19 06:23

**What it validates:** Document and consistently follow change management

**Why it matters:** Verifies that a change management procedure is documented and that the process is being followed by checking for stored Terraform plan files in S3.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path procedures/change-management-procedure.md`
   *Check for the existence of the change management procedure document.*

2. `aws s3 ls s3://mks-states/plans/ --recursive`
   *Check S3 for stored Terraform plans as evidence that the change process is followed.*

## Latest Results

PASS Excellent 10/10 (100%): PASS [Documentation] Comprehensive change management procedure found (size: 3747 bytes).
- PASS [Evidence] Found 2 recent Terraform plan artifact(s) in S3, proving change process execution.

---
*Generated 2025-11-19 06:23 UTC*