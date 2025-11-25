# KSI-IAM-06: Automatically disable or otherwise secure accounts with privileged access in response to suspicious activity

## Overview

**Category:** Identity and Access Management
**Status:** PASS
**Last Check:** 2025-11-25 08:21

**What it validates:** Automatically disable or otherwise secure accounts with privileged access in response to suspicious activity

**Why it matters:** Validates a multi-layered automated response system, including threat detection (GuardDuty, Security Hub), event triggering (EventBridge), and automated actions (Lambda, Alarms).

## Validation Method

1. `aws guardduty list-detectors --output json`
   *Validates the presence of an automated threat detection service.*

2. `aws securityhub describe-hub --output json`
   *Checks for a centralized hub for managing security events.*

3. `aws events list-rules --output json`
   *Checks for EventBridge rules that trigger actions on security events.*

4. `aws lambda list-functions --output json`
   *Identifies custom Lambda functions designed for automated security responses.*

5. `aws cloudwatch describe-alarms --output json`
   *Checks for CloudWatch alarms that monitor for and notify on security events.*

## Latest Results

PASS Excellent 10/10 (100%): PASS [Detection] Advanced threat detection is active with 1 GuardDuty detector(s).
- PASS [Detection] Security Hub is enabled, providing a centralized view for security events.
- PASS [Triggering] A robust event-driven security framework is in place with 7 relevant EventBridge rules.
- PASS [Response] Custom automated response actions likely implemented via 3 security-focused Lambda functions.
- PASS [Response] Proactive monitoring and alerting likely configured with 13 security-focused CloudWatch Alarms.

---
*Generated 2025-11-25 08:31 UTC*