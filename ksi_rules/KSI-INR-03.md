# KSI-INR-03: Generate after action reports and regularly incorporate lessons learned into operations.

## Overview

**Category:** Incident Reporting
**Status:** PASS
**Last Check:** 2025-11-24 12:24

**What it validates:** Generate after action reports and regularly incorporate lessons learned into operations.

**Why it matters:** Validates automated incident response from basic CloudWatch alarms to enterprise-grade SOAR platforms and intelligent threat response

## Validation Method

1. `aws securityhub get-findings --max-results 50 --output json`
   *Check Security Hub for incident detection and automated response triggers*

2. `aws lambda list-functions --output json`
   *Validate Lambda functions for automated incident response actions*

3. `aws securityhub describe-standards --output json`
   *Check Security Hub standards for automated compliance monitoring*

4. `aws securityhub get-enabled-standards --output json`
   *Validate enabled Security Hub standards for continuous monitoring*

## Latest Results

PASS Excellent 10/10 (100%): PASS Incident analysis capability: Security Hub findings accessible.
- PASS Automated reporting: 4 Lambda functions for after-action reporting deployed.
- PASS Continuous improvement framework: Security Hub standards definitions available.
- PASS Standards actively enabled: 1 Security Hub standard(s) are enabled and READY.

---
*Generated 2025-11-24 12:34 UTC*