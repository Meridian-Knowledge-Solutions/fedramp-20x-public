# KSI-CMT-05: Evaluate risk and potential impact of any change (Superseded by KSI-AFR-05)

## Overview

**Category:** Change Management
**Status:** Not validated

**What it validates:** Evaluate risk and potential impact of any change (Superseded by KSI-AFR-05)

**Why it matters:** Performs a hybrid check: 1) A live call to AWS CodeCommit to verify the risk assessment document exists. 2) A live call to S3 to verify Terraform plans are being stored as evidence of impact analysis.

## Validation Method

1. `aws codecommit get-file --repository-name security-governance --commit-specifier main --file-path procedures/change-risk-assessment.md`
   *Live check for the risk assessment procedure in CodeCommit.*

2. `aws s3 ls s3://mks-states/plans/ --recursive`
   *Check S3 for stored Terraform plans as evidence of impact assessment.*

---
<<<<<<< Updated upstream
*Generated 2025-11-23 00:55 UTC*
=======
*Generated 2025-11-23 01:18 UTC*
>>>>>>> Stashed changes
