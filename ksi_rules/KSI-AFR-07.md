# KSI-AFR-07: Develop secure by default configurations and provide guidance for secure configuration of the cloud service offering to customers in alignment with the FedRAMP Recommended Secure Configuration (RSC) guidance standard and persistently address all related requirements and recommendations.

## Overview

**Category:** Other
**Status:** FAIL
**Last Check:** 2025-11-22 06:22

**What it validates:** Develop secure by default configurations and provide guidance for secure configuration of the cloud service offering to customers in alignment with the FedRAMP Recommended Secure Configuration (RSC) guidance standard and persistently address all related requirements and recommendations.

**Why it matters:** Validates the existence of the Secure Configuration Guide (Source of Truth).

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path fedramp-20x-secure-configuration.md`
   *Check for Secure Configuration Guide.*

## Latest Results

- FAIL Insufficient 0/5 (0%): FAIL [Documentation] Secure Configuration Guide NOT found in the expected CodeCommit path.

---
*Generated 2025-11-22 06:34 UTC*