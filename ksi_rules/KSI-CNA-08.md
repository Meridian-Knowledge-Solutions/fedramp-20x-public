# KSI-CNA-08: Use automated services to persistently assess the security posture of all machine-based information resources and automatically enforce their intended operational state.

## Overview

**Category:** Cloud Native Architecture
**Status:** PASS
**Last Check:** 2025-11-25 12:25

**What it validates:** Use automated services to persistently assess the security posture of all machine-based information resources and automatically enforce their intended operational state.

**Why it matters:** Validates a multi-layered automation strategy, including persistent assessment (Security Hub, Config) and automated enforcement (SSM Associations, custom Lambda functions).

## Validation Method

1. `aws securityhub get-enabled-standards --output json`
   *Validates the foundational framework for persistent assessment.*

2. `aws configservice describe-config-rules --output json`
   *Measures the breadth of persistent security assessment.*

3. `aws configservice describe-configuration-recorder-status --output json`
   *Verifies that assessment data is actively being recorded.*

4. `aws securityhub describe-hub --output json`
   *Checks for centralized visibility via Security Hub.*

5. `aws configservice describe-configuration-aggregators --output json`
   *Checks for enterprise-wide visibility via Config aggregators.*

6. `aws ssm list-associations --output json || echo '{"Associations": []}'`
   *Validates automated enforcement via SSM State Manager associations.*

7. `aws lambda list-functions --output json`
   *Identifies custom, event-driven enforcement capabilities via Lambda.*

## Latest Results

PASS Strong 10/12 (83%): PASS Measurement Framework: Basic - 1/1 Security Hub standard(s) READY.
- PASS Measurement Instruments: Extensive - 333 AWS Config rules deployed.
- PASS Active Measurement: At least one Config recorder is actively capturing data successfully.
- PASS Measurement Visibility: Centralized - Security Hub is enabled.

---
*Generated 2025-11-25 12:35 UTC*