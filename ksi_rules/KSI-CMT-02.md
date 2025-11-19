# KSI-CMT-02: Use self-service templates and image repositories for provisioning

## Overview

**Category:** Change Management
**Status:** PASS
**Last Check:** 2025-11-19 08:14

**What it validates:** Use self-service templates and image repositories for provisioning

**Why it matters:** Validates comprehensive self-service provisioning from basic AMIs to enterprise-grade service catalogs and automated deployment templates

## Validation Method

1. `aws cloudformation list-stacks --stack-status-filter CREATE_COMPLETE UPDATE_COMPLETE --output json`
   *Check CloudFormation stacks for infrastructure templates*

2. `aws ec2 describe-instances --query 'Reservations[*].Instances[*].[InstanceId,ImageId,LaunchTime]' --output json`
   *Validate EC2 instances using standardized AMIs*

3. `aws ec2 describe-launch-templates --output json`
   *Check launch templates for self-service provisioning*

4. `aws autoscaling describe-auto-scaling-groups --output json`
   *Validate auto-scaling using standardized templates*

5. `aws lambda list-functions --output json`
   *Check Lambda functions for serverless self-service deployment*

6. `aws deploy list-applications --output json`
   *Validate CodeDeploy applications for automated deployment*

7. `aws ecr describe-repositories --output json`
   *Check ECR repositories for container image templates*

8. `aws servicecatalog search-products --output json`
   *Validate Service Catalog for self-service product templates*

9. `aws organizations describe-organization --output json`
   *Check organization-wide standardized provisioning policies*

## Latest Results

PASS Excellent 20/20 (100%): PASS External Terraform Evidence: 10 managed files documented.
- PASS Automated immutable deployment: GitHub Actions CI/CD integration detected.
- PASS External Terraform management approach documented.
- 🎯 Infrastructure as Code (IaC) validated via external Terraform evidence.
- PASS Immutable serverless-first architecture: 20 Lambda functions detected (inherently immutable).
- PASS Enterprise-wide immutable deployment governance: AWS Organizations enables centralized policies.
- PASS Advanced organization features: SCPs available for immutable deployment policy enforcement.

---
*Generated 2025-11-19 08:15 UTC*