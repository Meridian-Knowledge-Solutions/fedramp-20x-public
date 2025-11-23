# KSI-TPR-04: Automatically monitor third party software information resources for upstream vulnerabilities using mechanisms that may include contractual notification requirements or active monitoring services.

## Overview

**Category:** Third-Party Information Resources
**Status:** PASS
**Last Check:** 2025-11-23 08:20

**What it validates:** Automatically monitor third party software information resources for upstream vulnerabilities using mechanisms that may include contractual notification requirements or active monitoring services.

**Why it matters:** Validates comprehensive vulnerability scanning from basic Inspector to enterprise-grade continuous scanning and automated remediation

## Validation Method

1. `aws inspector2 get-configuration --output json`
   *Check Inspector configuration for vulnerability scanning*

2. `aws inspector2 list-findings --filter-criteria '{"componentType":[{"comparison":"EQUALS","value":"OPERATING_SYSTEM"}]}' --max-results 50 --output json`
   *Validate OS vulnerability findings from Inspector*

3. `aws inspector2 list-findings --filter-criteria '{"componentType":[{"comparison":"EQUALS","value":"APPLICATION"}]}' --max-results 50 --output json`
   *Check application vulnerability findings from Inspector*

4. `aws inspector2 list-findings --filter-criteria '{"findingStatus":[{"comparison":"EQUALS","value":"ACTIVE"}]}' --max-results 100 --output json`
   *Validate active vulnerability findings requiring remediation*

5. `aws inspector2 list-coverage --filter-criteria '{"resourceType":[{"comparison":"EQUALS","value":"AWS_EC2_INSTANCE"}]}' --max-results 100 --output json`
   *Check Inspector coverage for EC2 instances*

6. `aws ssm describe-instance-information --output json`
   *Validate SSM agent deployment for vulnerability management*

## Latest Results

PASS Excellent 11/11 (100%): PASS Inspector EC2 vulnerability scanning successfully enabled.
- PASS Inspector OS vulnerability scanning is active (0 findings found).
- PASS Inspector Application vulnerability scanning is active (0 findings found).
- PASS EC2 Inspector coverage verified: 9 instances covered (6 actively scanning).
- PASS Package inventory capability: 6/6 instances online via SSM for dependency tracking.
- PASS Active vulnerability monitoring: Inspector is tracking 100 ACTIVE findings.
- 📊 Monitoring Maturity: 5/5 capabilities detected (100% coverage).

---
*Generated 2025-11-23 08:30 UTC*