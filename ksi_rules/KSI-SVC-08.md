# KSI-SVC-08: Do not introduce or leave behind residual elements that could negatively affect confidentiality, integrity, or availability of federal customer data during operations.

## Overview

**Category:** Service Configuration
**Status:** FAIL
**Last Check:** 2025-11-22 18:24

**What it validates:** Do not introduce or leave behind residual elements that could negatively affect confidentiality, integrity, or availability of federal customer data during operations.

**Why it matters:** Validates a comprehensive IaC strategy by checking for: 1) Live IaC usage/management (Terraform .tfstate/.tfplan files in S3). 2) Automated security controls (Checkov/SARIF/automation artifacts).

## Validation Method

1. `aws s3 ls s3://mks-states/ --recursive`
   *Check S3 bucket for Terraform state files (.tfstate) as proof of IaC usage and plan files (.tfplan) as proof of a managed workflow.*

## Latest Results

Below threshold: 6/10 (60.0%) - requires 64.0% for MODERATE impact: FAIL [IaC Usage] Access Denied: Validator cannot list s3://mks-states/. Update Bucket Policy.
- PASS [IaC Controls] Security scanning (Checkov) verified.
- PASS [IaC Controls] Automated testing proof verified.

---
*Generated 2025-11-22 18:34 UTC*