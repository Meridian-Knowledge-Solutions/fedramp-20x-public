# KSI-MLA-03: Rapidly detect and remediate or mitigate vulnerabilities (Superseded by KSI-AFR-04)

## Overview

**Category:** Monitoring, Logging, and Auditing
**Status:** Not validated

**What it validates:** Rapidly detect and remediate or mitigate vulnerabilities (Superseded by KSI-AFR-04)

**Why it matters:** Validates comprehensive vulnerability detection, including Config rules, Inspector scanning, active findings, patch management, automated response, and enterprise governance.

## Validation Method

1. `aws securityhub get-enabled-standards --region us-east-1 --output json`
   *Check Security Hub enabled standards for vulnerability detection*

2. `aws inspector2 get-configuration --output json`
   *Validate Inspector for continuous vulnerability scanning*

3. `aws securityhub get-findings --filters '{"RecordState":[{"Value":"ACTIVE","Comparison":"EQUALS"}],"WorkflowStatus":[{"Value":"NEW","Comparison":"EQUALS"}]}' --max-results 50 --output json`
   *Check active Security Hub findings for rapid detection*

4. `aws ssm describe-patch-baselines --output json`
   *Validate patch baselines for automated vulnerability remediation*

5. `aws lambda list-functions --output json`
   *Check Lambda functions for automated remediation workflows*

6. `aws cloudwatch describe-alarms --output json`
   *Validate CloudWatch alarms for vulnerability detection alerts*

7. `aws configservice describe-config-rules --output json`
   *Check Config Rules for configuration vulnerability detection.*

8. `aws organizations describe-organization --output json`
   *Check organization-wide vulnerability management policies*

---
*Generated 2025-11-24 03:01 UTC*