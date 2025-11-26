# KSI-CNA-03: Use logical networking and related capabilities to enforce traffic flow controls.

## Overview

**Category:** Cloud Native Architecture
**Status:** PASS
**Last Check:** 2025-11-26 06:27

**What it validates:** Use logical networking and related capabilities to enforce traffic flow controls.

**Why it matters:** Validates strict public access control from basic public subnet restrictions to enterprise-grade private connectivity with minimal internet exposure

## Validation Method

1. `aws ec2 describe-route-tables --output json`
   *Check routing tables for public internet gateway associations*

2. `aws ec2 describe-network-acls --output json`
   *Validate network ACLs for public access restrictions*

3. `aws ec2 describe-vpc-endpoints --output json`
   *Check VPC endpoints for private AWS service connectivity without internet*

4. `aws ec2 describe-transit-gateways --output json`
   *Validate transit gateway configurations for private inter-VPC connectivity*

5. `aws elbv2 describe-load-balancers --output json`
   *Check load balancer schemes (internal vs internet-facing) as managed access points*

6. `aws ec2 describe-nat-gateways --output json`
   *Validate NAT gateways as controlled egress points for private resources*

7. `aws logs describe-log-groups --log-group-name-prefix '/aws/vpc/' --output json`
   *Check VPC Flow Logs for monitoring public access patterns*

## Latest Results

PASS Excellent 17/16 (106%): PASS Logical routing infrastructure: 5/5 route tables with intentional traffic flows
- PASS Advanced routing patterns: 4 route tables with custom traffic control
- PASS Advanced network access control: 1/1 NACLs with custom traffic flow policies
- PASS Advanced service routing: 7 VPC endpoints (1 gateway, 4 interface, 2 GWLB)
- PASS Single-VPC architecture: No Transit Gateways needed (appropriate design)
- PASS Application-layer traffic control: 1 Application Load Balancers
- PASS Controlled egress routing: 1 active NAT Gateways
- PASS Traffic flow monitoring: 2 VPC Flow Log groups found.

---
*Generated 2025-11-26 06:37 UTC*