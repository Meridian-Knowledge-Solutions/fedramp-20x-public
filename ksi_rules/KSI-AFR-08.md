# KSI-AFR-08: Operate a secure inbox to receive critical communication from FedRAMP and other government entities in alignment with FedRAMP Security Inbox (FSI) requirements and persistently address all related requirements and recommendations.

## Overview

**Category:** Other
**Status:** PASS
**Last Check:** 2025-11-21 06:24

**What it validates:** Operate a secure inbox to receive critical communication from FedRAMP and other government entities in alignment with FedRAMP Security Inbox (FSI) requirements and persistently address all related requirements and recommendations.

**Why it matters:** Validates the existence of the Security Inbox procedures document.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --file-path procedures/security-inbox-procedures.md`
   *Check for Security Inbox Procedures.*

## Latest Results

PASS Excellent 5/5 (100%): PASS [Documentation] Security Inbox Procedures found in CodeCommit.
- PASS [Quality] Document appears substantial (3532 bytes).

---
*Generated 2025-11-21 06:36 UTC*