# KSI-PIY-04: Monitor the effectiveness of building security and privacy considerations into the Software Development Lifecycle and aligning with CISA Secure By Design principles.

## Overview

**Category:** Policy and Inventory
**Status:** PASS
<<<<<<< Updated upstream
**Last Check:** 2025-11-25 12:25
=======
**Last Check:** 2025-11-25 12:49
>>>>>>> Stashed changes

**What it validates:** Monitor the effectiveness of building security and privacy considerations into the Software Development Lifecycle and aligning with CISA Secure By Design principles.

**Why it matters:** Validates comprehensive authorized software management from basic allow-lists to enterprise-grade application control and compliance tracking

## Validation Method

1. `aws codebuild list-projects --output json`
   *Check CodeBuild for authorized software deployment pipelines*

2. `aws codepipeline list-pipelines --output json`
   *Validate CodePipeline for authorized software deployment*

3. `aws lambda list-functions --output json`
   *Check Lambda functions for authorized serverless software*

4. `aws organizations describe-organization --output json`
   *Validate organization-wide authorized software policies*

## Latest Results

PASS Excellent 7/8 (88%): PASS Build Security Integration: Found 3 security-focused CodeBuild projects.
- PASS Pipeline Security Gates: Found 1 CodePipeline workflows (assumes security stages).
- PASS Security Automation Functions: Found 1 Lambda function for SDLC security.
- PASS Development Governance: AWS Organizations detected (enables central policies/SCPs).
- 📊 SDLC Security Maturity: 4/4 capabilities detected (100% coverage).

---
<<<<<<< Updated upstream
*Generated 2025-11-25 12:35 UTC*
=======
*Generated 2025-11-25 12:59 UTC*
>>>>>>> Stashed changes
