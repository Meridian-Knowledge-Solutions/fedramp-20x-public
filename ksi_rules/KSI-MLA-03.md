# KSI-MLA-03: Rapidly detect and remediate or mitigate vulnerabilities

## Overview

**Category:** Monitoring, Logging, and Auditing
**Status:** PASS
**Last Check:** 2025-11-20 04:14

**What it validates:** Rapidly detect and remediate or mitigate vulnerabilities

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

## Latest Results

PASS Sufficient 12/18 (67%): PASS Automated vulnerability scanning: Inspector enabled for EC2, ECR.
- PASS Multi-service vulnerability coverage via Inspector (2 services).
- PASS Configuration vulnerability detection: 332 Config rules monitoring security posture.
- PASS Automated patch management capability: 17 patch baselines configured (17 custom).
- PASS Tailored remediation: 17 custom patch baselines for targeted response.
- PASS Real-time threat detection/alerting: 13 potentially security-related CloudWatch alarms.
- PASS Active threat analysis: 50 active security findings (1 critical, 7 high).
- PASS Enterprise vulnerability management: AWS Organizations enables centralized multi-account detection/management.
- PASS Multi-service vulnerability coverage: 4 AWS services integrated for detection/response.

---
*Generated 2025-11-20 04:14 UTC*