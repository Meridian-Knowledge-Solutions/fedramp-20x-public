# KSI-IAM-05: Separate duties between users

## Overview

**Category:** Identity and Access Management
**Status:** PASS
**Last Check:** 2025-10-31 05:21

**What it validates:** Separate duties between users

**Why it matters:** Validates a zero trust architecture by checking for a modern identity provider (Identity Center), network micro-segmentation, session-based credentials, and comprehensive logging.

## Validation Method

1. `aws sso-admin list-instances --output json || echo '{"Instances": []}'`
   *CRITICAL: Check for an active IAM Identity Center instance.*

2. `aws identitystore list-users --identity-store-id $(aws sso-admin list-instances --query 'Instances[0].IdentityStoreId' --output text 2>/dev/null) --output json || echo '{"Users": []}'`
   *Check Identity Center users to verify federation.*

3. `aws cloudtrail describe-trails --output json`
   *Validate CloudTrail configuration for comprehensive monitoring.*

4. `aws cloudtrail get-trail-status --name $(aws cloudtrail describe-trails --query 'trailList[0].TrailARN' --output text 2>/dev/null || echo 'none') --output json || echo '{"IsLogging": false}'`
   *CRITICAL: Check if the primary CloudTrail is actively logging using its full ARN.*

5. `aws ec2 describe-security-groups --output json`
   *Validate network micro-segmentation by analyzing security group rules.*

6. `aws ec2 describe-vpc-endpoints --output json`
   *Check for VPC endpoints to ensure secure, private communications.*

7. `aws sts get-caller-identity --output json`
   *Verify the use of temporary, session-based credentials.*

## Latest Results

PASS Excellent Zero Trust architecture (100%): PASS [Identity & MFA] Excellent identity practice in use (Federated/Assumed Role).
- PASS [Segmentation] Excellent network micro-segmentation: No security groups have overly permissive inbound rules.
- PASS [Credentials] Best practice followed: Using temporary, session-based credentials (assumed role).
- PASS [Secure Communications] Comprehensive private networking with 7 VPC endpoints.
- PASS [Monitoring] Comprehensive monitoring is active via CloudTrail ('meridianks-Management-events').

---
*Generated 2025-10-31 05:21 UTC*