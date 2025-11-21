# KSI-CMT-04: Always follow a documented change management procedure.

## Overview

**Category:** Change Management
**Status:** PASS
**Last Check:** 2025-11-21 04:15

**What it validates:** Always follow a documented change management procedure.

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
*Generated 2025-11-21 04:27 UTC*