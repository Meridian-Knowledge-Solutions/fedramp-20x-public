# KSI-RPL-02: Develop and maintain a recovery plan that aligns with the defined recovery objectives

## Overview

**Category:** Recovery Planning
**Status:** PASS
**Last Check:** 2025-10-09 20:38

**What it validates:** Develop and maintain a recovery plan that aligns with the defined recovery objectives

**Why it matters:** Validates recovery procedures in CodeCommit with RTO/RPO alignment and AWS Backup infrastructure validation.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path procedures/recovery-plan.md --output json`
   *Retrieve recovery plan documentation*

2. `aws codecommit get-file --repository-name security-governance --file-path procedures/recovery-testing.md --output json`
   *Retrieve recovery testing procedures*

3. `aws backup list-backup-plans --output json`
   *Validate AWS Backup plans alignment*

4. `aws backup list-backup-vaults --output json`
   *Validate backup vault configuration*

## Latest Results

WARNING Basic recovery planning (5/12): PASS AWS Backup plans configured: 2 plans
- PASS Backup vaults configured: 3 vaults
- WARNING Legacy recovery plan documentation - migrate to CodeCommit

---
*Generated 2025-10-09 20:38 UTC*