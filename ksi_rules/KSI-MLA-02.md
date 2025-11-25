# KSI-MLA-02: Regularly review and audit logs.

## Overview

**Category:** Monitoring, Logging, and Auditing
**Status:** PASS
**Last Check:** 2025-11-25 00:48

**What it validates:** Regularly review and audit logs.

**Why it matters:** Validates comprehensive log review from basic notification-driven processes to enterprise-grade automated analysis and compliance governance

## Validation Method

1. `aws cloudwatch describe-alarms --output json`
   *Check CloudWatch alarms for automated log review*

2. `aws logs describe-metric-filters --output json`
   *Validate metric filters for log pattern analysis*

3. `aws sns list-topics --output json`
   *Check SNS topics for log review notifications*

4. `aws logs describe-log-groups --output json`
   *Analyze log retention policies and compliance*

5. `aws cloudtrail lookup-events --max-items 10 --output json`
   *Check recent audit events for review validation*

6. `aws securityhub get-insights --output json`
   *Validate advanced log correlation and security analytics*

7. `aws lambda list-functions --output json`
   *Check custom log processing and automated review functions*

8. `aws organizations describe-organization --output json`
   *Validate enterprise-wide centralized log review capabilities*

## Latest Results

PASS Strong 15/18 (83%): PASS Log review notifications: 10 SNS topics available for alert delivery.
- PASS Manual review capability: 33 log groups available for analysis.
- PASS Automated log monitoring: 7 potentially log-related CloudWatch alarms found.
- PASS Security-focused review: 13 potentially security-related alarms detected.
- PASS Advanced log correlation: 1 Security Hub insights available for intelligent analysis.
- PASS Audit event analysis: 10 recent CloudTrail events retrieved via lookup (indicates analysis capability).
- PASS Custom log processing: 1 Lambda functions potentially used for advanced log analysis.
- PASS Compliance retention: 31/33 log groups with explicit retention policies (94%).
- PASS Long-term audit capability: 26/33 log groups meet compliance retention (>= 365 days).
- PASS Enterprise log aggregation: AWS Organizations enables centralized multi-account log review.

---
*Generated 2025-11-25 00:59 UTC*