# KSI-SVC-07: Use a consistent, risk-informed approach for applying security patches.

## Overview

**Category:** Service Configuration
**Status:** PASS
**Last Check:** 2025-11-25 04:24

**What it validates:** Use a consistent, risk-informed approach for applying security patches.

**Why it matters:** Validates comprehensive vulnerability management from basic patch baselines to enterprise-grade automated scanning, remediation, compliance monitoring, and governance.

## Validation Method

1. `aws ssm describe-patch-baselines --output json`
   *Check SSM patch baselines for vulnerability management.*

2. `aws ssm describe-instance-information --output json`
   *Validate SSM managed instances for patch compliance.*

3. `aws ssm describe-patch-groups --output json`
   *Check patch groups for organized vulnerability remediation.*

4. `aws ssm list-documents --document-filter-list key=DocumentType,value=Automation --output json`
   *Validate SSM automation for scheduled patch deployment.*

5. `aws ssm describe-maintenance-windows --output json`
   *Check maintenance windows for scheduled patching operations.*

6. `aws inspector2 get-configuration --output json`
   *Validate Inspector for continuous vulnerability scanning.*

7. `aws ecr describe-repositories --output json`
   *Check ECR repositories for container image vulnerability scanning.*

8. `aws lambda list-layers --output json`
   *Validate Lambda layers for serverless vulnerability management.*

9. `aws configservice describe-config-rules --output json`
   *Check Config Rules for patch compliance monitoring.*

10. `aws organizations describe-organization --output json`
   *Check organization-wide vulnerability management policies.*

## Latest Results

PASS Sufficient 13/20 (65%): PASS Consistent patch management: 17 patch baselines configured.
- PASS Automated patch deployment capability: 6/6 instances with SSM agent online (100%).
- PASS Patch automation framework: 32 relevant SSM documents found.
- PASS Serverless patch management: 1 Lambda layers for runtime dependency management.
- PASS Patch compliance monitoring: 12 Config rules related to patch/SSM governance found.
- PASS Enterprise-wide patch governance: AWS Organizations enables centralized policies.
- PASS Advanced organization features: SCPs for patch management policy enforcement enabled.

---
*Generated 2025-11-25 04:34 UTC*