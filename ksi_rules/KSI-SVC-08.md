# KSI-SVC-08: Do not introduce or leave behind residual elements that could negatively affect confidentiality, integrity, or availability of federal customer data during operations.

## Overview

**Category:** Service Configuration
**Status:** FAIL
**Last Check:** 2025-11-22 01:14

**What it validates:** Do not introduce or leave behind residual elements that could negatively affect confidentiality, integrity, or availability of federal customer data during operations.

**Why it matters:** Validates a comprehensive IaC strategy by checking for: 1) Live IaC usage/management (Terraform .tfstate/.tfplan files in S3). 2) Automated security controls (Checkov/SARIF/automation artifacts).

## Validation Method

1. `aws s3 ls s3://mks-states/ --recursive`
   *Check S3 bucket for Terraform state files (.tfstate) as proof of IaC usage and plan files (.tfplan) as proof of a managed workflow.*

## Latest Results

Below threshold: 6/10 (60.0%) - requires 64.0% for MODERATE impact: WARNING [IaC] S3 bucket data (s3://mks-states/) unavailable or bucket not found.
- PASS [IaC Controls] IaC Scan Artifact ('checkov_scan_summary.json') found in CMT-03 evidence.
- PASS [IaC Controls] Testing Proof Artifact ('automated_testing_proof.json') found in CMT-03 evidence.

---
*Generated 2025-11-22 01:27 UTC*