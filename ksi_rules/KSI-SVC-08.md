# KSI-SVC-08: Use infrastructure as code to apply controls to the provisioning and management of resources

## Overview

**Category:** Service Configuration
**Status:** PASS
**Last Check:** 2025-10-16 06:43

**What it validates:** Use infrastructure as code to apply controls to the provisioning and management of resources

**Why it matters:** Validates a comprehensive IaC strategy by confirming the use of CloudFormation for deployments and AWS Config for tracking resource changes and detecting residual elements.

## Validation Method

1. `aws cloudformation list-stacks --output json`
   *Check for active CloudFormation stacks as primary evidence of IaC.*

2. `aws configservice describe-configuration-recorders --output json`
   *Verify that AWS Config is active for tracking changes and detecting residual elements.*

3. `aws lambda list-functions --output json`
   *Check for custom Lambda functions that support IaC or cleanup automation.*

## Latest Results

PASS Strong IaC implementation with foundational change tracking (50%): PASS [IaC] Infrastructure is managed as code via 19 active CloudFormation stacks, ensuring consistent lifecycle management.
- WARNING [Change Tracking] An AWS Config recorder exists but is not currently recording.

---
*Generated 2025-10-16 06:43 UTC*