# KSI-TPR-03: Identify and prioritize mitigation of potential supply chain risks

## Overview

**Category:** Third-Party Information Resources
**Status:** FAIL
**Last Check:** 2025-10-10 03:07

**What it validates:** Identify and prioritize mitigation of potential supply chain risks

**Why it matters:** Validates supply chain risk policies migrated from SSM to CodeCommit with approval workflow and risk-based policy tiers.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path policies/third-party-policies.json --output json`
   *Retrieve supply chain policies from CodeCommit*

2. `aws codecommit get-pull-request-approval-rules --pull-request-id $(aws codecommit list-pull-requests --repository-name security-governance --pull-request-status OPEN --query 'pullRequestIds[0]' --output text) --output json || echo '{"approvalRules": []}'`
   *Validate PR approval for policy changes*

3. `aws ssm get-parameter --name '/lms-compliance/policies' --output json || echo '{"Parameter": null}'`
   *Check legacy SSM policies (migration validation)*

4. `aws codecommit get-differences --repository-name security-governance --after-commit-specifier refs/heads/main --output json`
   *Audit trail of supply chain policy decisions*

## Latest Results

- FAIL Insufficient supply chain risk management (-1/13): WARNING Legacy SSM policies detected - migration recommended

---
*Generated 2025-10-10 03:07 UTC*