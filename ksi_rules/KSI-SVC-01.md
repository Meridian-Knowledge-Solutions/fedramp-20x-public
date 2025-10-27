# KSI-SVC-01: Maintain hardened system images and configurations

## Overview

**Category:** Service Configuration
**Status:** PASS
**Last Check:** 2025-10-27 18:57

**What it validates:** Maintain hardened system images and configurations

**Why it matters:** Validates comprehensive system hardening from basic security groups to enterprise-grade patch management and automated configuration enforcement

## Validation Method

1. `aws ec2 describe-security-groups --output json`
   *Check security group configurations for system hardening*

2. `aws ec2 describe-instances --output json`
   *Validate EC2 instances using hardened AMIs and configurations*

3. `aws ssm describe-instance-information --output json`
   *Check SSM agent deployment for configuration management*

4. `aws ssm describe-patch-baselines --output json`
   *Validate patch baselines for automated security updates*

5. `aws configservice describe-config-rules --output json`
   *Check Config rules for continuous hardening compliance*

6. `aws ec2 describe-network-acls --output json`
   *Validate network ACLs for defense-in-depth hardening*

7. `aws guardduty list-detectors --output json`
   *Check GuardDuty for threat detection on hardened systems*

8. `aws wafv2 list-web-acls --scope REGIONAL --output json`
   *Validate WAF rules for application-layer hardening*

9. `aws inspector2 get-configuration --output json`
   *Check Inspector for vulnerability scanning of system images*

10. `aws organizations describe-organization --output json`
   *Validate organization-wide hardening policies and SCPs*

11. `aws ec2 describe-vpc-endpoints --output json`
   *Check VPC endpoints for private connectivity and reduced attack surface*

## Latest Results

PASS Excellent network and system hardening with comprehensive governance (90%): PASS Network hardening foundation: 15 security groups (15 hardened, 0 require review)
- PASS System configuration management: 6 instances configured
- PASS Comprehensive system management: 5/6 instances under SSM (83% coverage)
- PASS Automated patch management: 17 patch baselines configured
- PASS Configuration compliance: 327 active Config rules (327 security-focused)
- PASS Threat detection enabled: 1 GuardDuty detectors monitoring for threats
- PASS Application layer protection: 1 Web ACLs configured
- PASS Secure service access: 7 VPC endpoints (4 interface, 3 gateway)
- PASS Enterprise-wide security governance: AWS Organizations enables centralized hardening policies
- PASS Advanced organization features: SCPs and advanced governance capabilities enabled

---
*Generated 2025-10-27 18:57 UTC*