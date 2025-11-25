# KSI-CED-03: Require and monitor the effectiveness of role-specific training provided to development and engineering staff that covers best practices for delivering secure software.

## Overview

**Category:** Cybersecurity Education
**Status:** FAIL
**Last Check:** 2025-11-25 00:48

**What it validates:** Require and monitor the effectiveness of role-specific training provided to development and engineering staff that covers best practices for delivering secure software.

**Why it matters:** Validates security awareness training from basic phishing tests to enterprise-grade continuous awareness programs and behavior analytics

## Validation Method

1. `aws lambda list-functions --output json`
   *Check for security awareness automation functions*

2. `aws events list-rules --output json`
   *Check for automated training delivery triggers*

3. `aws organizations describe-organization --output json`
   *Check for enterprise training governance policies*

## Latest Results

FAIL Insufficient 3/7 (43%): PASS Development security automation: Found 2 potentially security-related Lambda function(s).
- PASS Enterprise governance: AWS Organizations detected (enables central training/security policies).

---
*Generated 2025-11-25 00:59 UTC*