# KSI-IAM-06: Implement fine-grained automated actions on security events related to authentication and access control

## Overview

**Category:** Identity and Access Management
**Status:** PASS
**Last Check:** 2025-11-15 16:16

**What it validates:** Implement fine-grained automated actions on security events related to authentication and access control

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

PASS Excellent automated security response capabilities (100%): PASS [Detection] Advanced threat detection is active with 1 GuardDuty detector(s).
- PASS [Detection] Security Hub is enabled, providing a centralized view for security events.
- PASS [Triggering] A robust event-driven security framework is in place with 5 relevant EventBridge rules.
- PASS [Response] Custom automated response actions are implemented via 3 security-focused Lambda functions.
- PASS [Response] Proactive monitoring and alerting is configured with 9 security-focused CloudWatch Alarms.

---
*Generated 2025-11-15 16:16 UTC*