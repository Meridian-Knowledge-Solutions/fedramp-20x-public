# KSI-SVC-09: Persistently validate the authenticity and integrity of communications between machine-based information resources using automation.

## Overview

**Category:** Service Configuration
**Status:** PASS
**Last Check:** 2025-11-22 18:24

**What it validates:** Persistently validate the authenticity and integrity of communications between machine-based information resources using automation.

**Why it matters:** Validates the end-to-end use of modern, secure communication protocols (TLS 1.2+) across the infrastructure.

## Validation Method

1. `aws acm list-certificates --output json`
   *Check for valid, in-use ACM certificates.*

2. `aws elbv2 describe-ssl-policies --output json`
   *Get all available SSL policies for reference.*

3. `for arn in $(aws elbv2 describe-load-balancers --query 'LoadBalancers[].LoadBalancerArn' --output text); do aws elbv2 describe-listeners --load-balancer-arn $arn --output json; done`
   *CRITICAL: Check the SSL policies actively used by load balancer listeners.*

4. `aws ec2 describe-vpc-endpoints --output json`
   *Verify that internal traffic uses secure, private endpoints.*

5. `aws cloudwatch describe-alarms --query 'MetricAlarms[?contains(AlarmDescription, `Certificate`) || contains(AlarmName, `SSL`)]' --output json`
   *Check for specific alarms that monitor certificate expiry or TLS issues.*

6. `aws lambda list-functions --query 'Functions[?contains(FunctionName, `cert`) || contains(FunctionName, `ssl`)]' --output json`
   *Look for Lambda functions related to certificate rotation or lifecycle management.*

## Latest Results

PASS Strong 8/10 (80%): PASS [Certificate Health] All 2 checked ACM certificates are valid.
- PASS [TLS Enforcement] All 1 HTTPS listeners enforce strict TLS 1.2+.
- PASS [Internal Security] Secure private communication enforced via 7 VPC Endpoints.

---
*Generated 2025-11-22 18:34 UTC*