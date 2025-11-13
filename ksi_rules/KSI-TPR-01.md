# KSI-TPR-01: Document the cloud service provider (CSP) in the system security policy

## Overview

**Category:** Third-Party Information Resources
**Status:** PASS
<<<<<<< Updated upstream
**Last Check:** 2025-11-13 12:18
=======
**Last Check:** 2025-11-13 12:25
>>>>>>> Stashed changes

**What it validates:** Document the cloud service provider (CSP) in the system security policy

**Why it matters:** Validates CSP documentation from basic AWS account details to enterprise-grade shared responsibility model and service integration policies

## Validation Method

1. `aws lambda list-functions --query 'Functions[?contains(FunctionName, `policy`) || contains(FunctionName, `compliance`)]' --output json`
   *Check for policy management Lambda functions*

2. `aws logs describe-log-groups --log-group-name-prefix '/aws/lambda/lms-policy' --output json`
   *Validate policy service logging for documentation tracking*

3. `aws ssm get-parameter --name '/lms-compliance/policies' --output json || echo '{"Parameter": null}'`
   *Check SSM Parameter Store for centralized policy storage*

## Latest Results

- PASS Third-party resources identified via static configuration: PASS Static discovery: 5 third-party services identified from whitelist

---
<<<<<<< Updated upstream
*Generated 2025-11-13 12:19 UTC*
=======
*Generated 2025-11-13 12:25 UTC*
>>>>>>> Stashed changes
