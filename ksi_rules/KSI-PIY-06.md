# KSI-PIY-06: Monitor the effectiveness of the organization's investments in achieving security objectives.

## Overview

**Category:** Policy and Inventory
**Status:** PASS
**Last Check:** 2025-11-22 02:45

**What it validates:** Monitor the effectiveness of the organization's investments in achieving security objectives.

**Why it matters:** Validates organizational commitment to security through active engagement, tooling investment, and deployed monitoring capabilities.

## Validation Method

1. `aws cloudtrail lookup-events --lookup-attributes AttributeKey=EventName,AttributeValue=ConsoleLogin --start-time $(date -u -d '30 days ago' '+%Y-%m-%dT%H:%M:%S') --max-items 50 --output json`
   *Measure active security team engagement via console logins.*

2. `aws cloudtrail lookup-events --lookup-attributes AttributeKey=EventName,AttributeValue=PutConfigRule --start-time $(date -u -d '90 days ago' '+%Y-%m-%dT%H:%M:%S') --max-items 50 --output json`
   *Measure security engineering activity via Config rule deployments.*

3. `aws cloudtrail lookup-events --lookup-attributes AttributeKey=EventName,AttributeValue=PutMetricAlarm --start-time $(date -u -d '90 days ago' '+%Y-%m-%dT%H:%M:%S') --max-items 50 --output json`
   *Measure security engineering activity via CloudWatch alarm deployments.*

4. `aws configservice describe-config-rules --output json`
   *Count the total number of deployed Config rules.*

5. `aws cloudwatch describe-alarms --output json`
   *Get all CloudWatch alarms for security analysis.*

6. `aws lambda list-functions --output json`
   *Get all Lambda functions for security analysis.*

## Latest Results

PASS Excellent 10/10 (100%): PASS [Engagement] High security team activity detected: 50 recent logins across 4 user(s).
- PASS [Engineering] Active security engineering: 50 recent Config Rule deployment events detected.
- PASS [Engineering] Active security engineering: 13 recent CloudWatch Alarm deployment events detected.
- PASS [Capabilities] Comprehensive compliance coverage with 333 AWS Config rules deployed.
- PASS [Capabilities] Strong security monitoring indicated by 13 potentially security-related alarms.
- PASS [Capabilities] Automated security response capability suggested by 3 potentially security-related Lambda functions.

---
*Generated 2025-11-22 02:58 UTC*