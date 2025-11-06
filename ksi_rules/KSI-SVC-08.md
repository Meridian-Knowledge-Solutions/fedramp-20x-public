# KSI-SVC-08: Use infrastructure as code to apply controls to the provisioning and management of resources.

## Overview

**Category:** Service Configuration
**Status:** Not validated

**What it validates:** Use infrastructure as code to apply controls to the provisioning and management of resources.

**Why it matters:** Validates a comprehensive, Terraform-based IaC strategy by checking for live IaC state (.tfstate files) and managed changes (.tfplan files) in S3, supplemented by artifact checks for security controls.

## Validation Method

1. `aws s3 ls s3://mks-states/ --recursive`
   *Check S3 bucket for Terraform state files (.tfstate) as proof of IaC usage and plan files (.tfplan) as proof of a managed workflow.*

---
*Generated 2025-11-06 04:39 UTC*