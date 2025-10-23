# KSI-CNA-08: Use automated services to persistently assess and enforce secure operations

## Overview

**Category:** Cloud Native Architecture
**Status:** PASS
**Last Check:** 2025-10-23 06:50

**What it validates:** Use automated services to persistently assess and enforce secure operations

**Why it matters:** Validates a multi-layered automation strategy, including persistent assessment (Security Hub, Config) and automated enforcement (SSM Associations, custom Lambda functions).

## Validation Method

1. `aws securityhub get-enabled-standards --output json`
   *Validates the foundational framework for persistent assessment.*

2. `aws configservice describe-config-rules --output json`
   *Measures the breadth of persistent security assessment.*

3. `aws configservice describe-configuration-recorder-status --output json`
   *Verifies that assessment data is actively being recorded.*

4. `aws ssm list-associations --output json || echo '{"Associations": []}'`
   *Validates automated enforcement via SSM State Manager associations.*

5. `aws lambda list-functions --output json`
   *Identifies custom, event-driven enforcement capabilities via Lambda.*

## Latest Results

Excellent measurement posture (75%): Basic framework: 1 Security Hub standard(s)
- Extensive instrumentation: 327 Config rules
- Active measurement: Config recorder capturing data
- Limited visibility: No central aggregation

---
*Generated 2025-10-23 06:50 UTC*