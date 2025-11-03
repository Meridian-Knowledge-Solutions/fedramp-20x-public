# KSI-PIY-06: Have dedicated security staff and budget with executive support

## Overview

**Category:** Policy and Inventory
**Status:** PASS
**Last Check:** 2025-11-03 02:56

**What it validates:** Have dedicated security staff and budget with executive support

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

PASS Strong security commitment (80%): PASS [Engagement] High security team activity detected with 50 logins across 3 users.
- PASS [Engineering] Active security engineering: 50 recent Config Rule deployments.
- PASS [Engineering] Active security engineering: 13 recent CloudWatch Alarm deployments.
- PASS [Capabilities] Comprehensive compliance coverage with 327 AWS Config rules deployed.
- PASS [Capabilities] Automated security response is enabled with 3 specialized Lambda functions.

---
*Generated 2025-11-03 02:56 UTC*