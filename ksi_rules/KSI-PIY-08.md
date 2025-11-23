# KSI-PIY-08: Measure executive support via active budgetary controls and financial commitment.

## Overview

**Category:** Policy and Inventory
**Status:** FAIL
<<<<<<< Updated upstream
**Last Check:** 2025-11-23 06:18
=======
**Last Check:** 2025-11-23 06:41
>>>>>>> Stashed changes

**What it validates:** Measure executive support via active budgetary controls and financial commitment.

**Why it matters:** Validates executive engagement by confirming: 1. Active AWS Budgets (Financial Governance). 2. Actual financial spend (Resource Commitment). 3. Anomaly Detection (Proactive Oversight).

## Validation Method

1. `aws sts get-caller-identity --query Account --output text | xargs -I {} aws budgets describe-budgets --account-id {} --output json`
   *Governance: Retrieves all budgets, including spending limits (Plan) and current actual spend (Reality).*

2. `aws ce get-anomaly-monitors --output json`
   *Oversight: Checks for active Cost Anomaly Detection monitors.*

## Latest Results

- No rule function found: evaluate_KSI_PIY_08

---
<<<<<<< Updated upstream
*Generated 2025-11-23 06:28 UTC*
=======
*Generated 2025-11-23 06:51 UTC*
>>>>>>> Stashed changes
