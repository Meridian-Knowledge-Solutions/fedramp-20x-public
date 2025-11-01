# KSI-MLA-07: Use log aggregation services that accept logs from CSO-provided services

## Overview

**Category:** Monitoring, Logging, and Auditing
**Status:** PASS
<<<<<<< Updated upstream
**Last Check:** 2025-11-01 12:19
=======
**Last Check:** 2025-11-01 12:30
>>>>>>> Stashed changes

**What it validates:** Use log aggregation services that accept logs from CSO-provided services

**Why it matters:** Validates comprehensive log aggregation from basic CloudWatch to enterprise-grade centralized SIEM and cross-account log collection

## Validation Method

1. `aws logs describe-log-groups --output json`
   *Check CloudWatch Log Groups for centralized log aggregation*

2. `aws cloudtrail describe-trails --output json`
   *Validate CloudTrail for organization-wide audit log aggregation*

3. `aws cloudwatch describe-alarms --output json`
   *Check CloudWatch alarms for aggregated log monitoring*

## Latest Results

PASS Good automated monitoring inventory - enhance coverage (75%): PASS Comprehensive log infrastructure: 31 log groups
- PASS Comprehensive audit coverage: 1 trails with multi-region
- PASS Good monitoring configuration: 13 CloudWatch alarms

---
<<<<<<< Updated upstream
*Generated 2025-11-01 12:19 UTC*
=======
*Generated 2025-11-01 12:30 UTC*
>>>>>>> Stashed changes
