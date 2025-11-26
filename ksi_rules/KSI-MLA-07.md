# KSI-MLA-07: Maintain a list of information resources and event types that will be monitored, logged, and audited, then do so.

## Overview

**Category:** Monitoring, Logging, and Auditing
**Status:** PASS
**Last Check:** 2025-11-26 00:37

**What it validates:** Maintain a list of information resources and event types that will be monitored, logged, and audited, then do so.

**Why it matters:** Validates comprehensive log aggregation from basic CloudWatch to enterprise-grade centralized SIEM and cross-account log collection

## Validation Method

1. `aws logs describe-log-groups --output json`
   *Check CloudWatch Log Groups for centralized log aggregation*

2. `aws cloudtrail describe-trails --output json`
   *Validate CloudTrail for organization-wide audit log aggregation*

3. `aws cloudwatch describe-alarms --output json`
   *Check CloudWatch alarms for aggregated log monitoring*

## Latest Results

PASS Excellent 8/8 (100%): PASS Comprehensive log infrastructure: 33 CloudWatch log groups found.
- PASS Comprehensive audit coverage: 1 trail(s) found, including multi-region and organization trail.
- PASS Comprehensive monitoring configuration: 13 CloudWatch alarms found.

---
*Generated 2025-11-26 00:47 UTC*