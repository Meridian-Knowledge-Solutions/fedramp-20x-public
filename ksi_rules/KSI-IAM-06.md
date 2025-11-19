# KSI-IAM-06: Implement fine-grained automated actions on security events related to authentication and access control

## Overview

**Category:** Identity and Access Management
**Status:** PASS
<<<<<<< Updated upstream
**Last Check:** 2025-11-19 12:14
=======
**Last Check:** 2025-11-19 12:24
>>>>>>> Stashed changes

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

PASS Excellent 10/10 (100%): PASS [Detection] Advanced threat detection is active with 1 GuardDuty detector(s).
- PASS [Detection] Security Hub is enabled, providing a centralized view for security events.
- PASS [Triggering] A robust event-driven security framework is in place with 7 relevant EventBridge rules.
- PASS [Response] Custom automated response actions likely implemented via 3 security-focused Lambda functions.
- PASS [Response] Proactive monitoring and alerting likely configured with 13 security-focused CloudWatch Alarms.

---
<<<<<<< Updated upstream
*Generated 2025-11-19 12:14 UTC*
=======
*Generated 2025-11-19 12:24 UTC*
>>>>>>> Stashed changes
