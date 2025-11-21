# KSI-AFR-08: Operate a secure inbox to receive critical communication from FedRAMP and other government entities in alignment with FedRAMP Security Inbox (FSI) requirements and persistently address all related requirements and recommendations.

## Overview

**Category:** Other
**Status:** FAIL
**Last Check:** 2025-11-21 02:46

**What it validates:** Operate a secure inbox to receive critical communication from FedRAMP and other government entities in alignment with FedRAMP Security Inbox (FSI) requirements and persistently address all related requirements and recommendations.

**Why it matters:** Validates the existence of the Security Inbox procedures document.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path procedures/security-inbox-procedures.md`
   *Check for Security Inbox Procedures.*

## Latest Results

- FAIL Insufficient 0/5 (0%): FAIL [Documentation] Security Inbox Procedures NOT found in the expected CodeCommit path.

---
*Generated 2025-11-21 02:59 UTC*