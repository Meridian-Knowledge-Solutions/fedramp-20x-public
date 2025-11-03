# KSI-CNA-08: Use automated services to persistently assess and enforce secure operations

## Overview

**Category:** Cloud Native Architecture
**Status:** Not validated

**What it validates:** Use automated services to persistently assess and enforce secure operations

**Why it matters:** Validates a multi-layered automation strategy, including persistent assessment (Security Hub, Config) and automated enforcement (SSM Associations, custom Lambda functions).

## Validation Method

1. `aws securityhub get-enabled-standards --output json`
   *Validates the foundational framework for persistent assessment.*

2. `aws configservice describe-config-rules --output json`
   *Measures the breadth of persistent security assessment.*

3. `aws configservice describe-configuration-recorder-status --output json`
   *Verifies that assessment data is actively being recorded.*

4. `aws securityhub describe-hub --output json`
   *Checks for centralized visibility via Security Hub. (Added for 'Measurement Visibility' score).*

5. `aws configservice describe-configuration-aggregators --output json`
   *Checks for enterprise-wide visibility via Config aggregators. (Added for 'Measurement Visibility' score).*

6. `aws ssm list-associations --output json || echo '{"Associations": []}'`
   *Validates automated enforcement via SSM State Manager associations.*

7. `aws lambda list-functions --output json`
   *Identifies custom, event-driven enforcement capabilities via Lambda.*

---
<<<<<<< Updated upstream
*Generated 2025-11-03 06:18 UTC*
=======
*Generated 2025-11-03 06:25 UTC*
>>>>>>> Stashed changes
