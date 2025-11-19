# KSI-SVC-08: Use infrastructure as code to apply controls to the provisioning and management of resources.

## Overview

**Category:** Service Configuration
**Status:** PASS
**Last Check:** 2025-11-19 06:23

**What it validates:** Use infrastructure as code to apply controls to the provisioning and management of resources.

**Why it matters:** Validates a comprehensive IaC strategy by checking for: 1) Live IaC usage/management (Terraform .tfstate/.tfplan files in S3). 2) Automated security controls (Checkov/SARIF/automation artifacts).

## Validation Method

1. `aws s3 ls s3://mks-states/ --recursive`
   *Check S3 bucket for Terraform state files (.tfstate) as proof of IaC usage and plan files (.tfplan) as proof of a managed workflow.*

## Latest Results

PASS Excellent 10/10 (100%): PASS [IaC Usage] Terraform state files (.tfstate) found in s3://mks-states/.
- PASS [IaC Management] Terraform plan files (.tfplan) found in s3://mks-states/plans/.
- PASS [IaC Controls] IaC Scan Artifact ('checkov_scan_summary.json') found in CMT-03 evidence.
- PASS [IaC Controls] Testing Proof Artifact ('automated_testing_proof.json') found in CMT-03 evidence.

---
*Generated 2025-11-19 06:23 UTC*