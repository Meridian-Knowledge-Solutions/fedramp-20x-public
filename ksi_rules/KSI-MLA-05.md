# KSI-MLA-05: Perform Infrastructure as Code and configuration evaluation and testing.

## Overview

**Category:** Monitoring, Logging, and Auditing
**Status:** PASS
**Last Check:** 2025-11-22 04:18

**What it validates:** Perform Infrastructure as Code and configuration evaluation and testing.

**Why it matters:** Validates comprehensive change tracking from basic CloudTrail and Config rules to enterprise-grade automated governance and compliance reporting

## Validation Method

1. `aws configservice describe-config-rules --output json`
   *Check Config Rules for compliance evaluation during change management*

2. `aws ssm describe-parameters --max-results 50 --output json`
   *Check SSM parameters for configuration change management*

3. `aws cloudtrail lookup-events --lookup-attributes AttributeKey=ResourceType,AttributeValue=AWS::CloudFormation::Stack --max-items 20 --output json`
   *Validate CloudTrail audit logs for configuration changes*

4. `aws resourcegroupstaggingapi get-resources --resource-type-filters cloudformation --output json`
   *Check resource tagging for change management governance*

5. `aws organizations describe-organization --output json`
   *Validate organization-wide change management policies*

## Latest Results

PASS Excellent 20/20 (100%): PASS Automated change management: Validated via external CI/CD evidence (GitHub Actions, Terraform).
- PASS IaC change process: Validated via external Terraform evidence (10 files).
- PASS Configuration compliance evaluation: 333 active Config rules detected.
- PASS Centralized configuration management: 7 SSM parameters found.
- PASS Resource governance: 7 resources found with IaC-related tags.
- PASS Deployment audit trail: 20 relevant change events found in CloudTrail.
- PASS Organizational infrastructure: Centralized account management (o-wfu71gr2nf).
- PASS Enterprise multi-account governance: AWS Organizations with ALL features enabled (SCPs available).

---
*Generated 2025-11-22 04:30 UTC*