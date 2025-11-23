# KSI-AFR-08: Operate a secure inbox to receive critical communication from FedRAMP and other government entities in alignment with FedRAMP Security Inbox (FSI) requirements and persistently address all related requirements and recommendations.

## Overview

**Category:** Other
**Status:** PASS
**Last Check:** 2025-11-23 03:47

**What it validates:** Operate a secure inbox to receive critical communication from FedRAMP and other government entities in alignment with FedRAMP Security Inbox (FSI) requirements and persistently address all related requirements and recommendations.

**Why it matters:** Technical validation: Verifies DNS MX records exist, email domain has proper authentication (SPF/DMARC), and procedures are documented.

## Validation Method

1. `nslookup -type=MX meridianks.com | grep 'mail exchanger' || echo 'No MX records found'`
   *DNS Check: Validates MX records exist for the domain to receive email.*

2. `nslookup -type=TXT meridianks.com | grep -i 'v=spf1' || echo 'No SPF record found'`
   *SPF Record: Validates Sender Policy Framework is configured for email authentication.*

3. `nslookup -type=TXT _dmarc.meridianks.com | grep -i 'v=dmarc1' || echo 'No DMARC record found'`
   *DMARC Record: Validates Domain-based Message Authentication policy exists.*

4. `aws codecommit get-file --repository-name security-governance --file-path procedures/security-inbox-procedures.md --output json`
   *Governance: Validates documented procedures exist for security inbox operations.*

## Latest Results

PASS Excellent 10/10 (100%): PASS [MX Records] 2 MX record(s) found (e.g., 10 meridianks-com.mail.eo.outlook.com.).
- PASS [SPF] Sender Policy Framework configured.
- PASS [DMARC] DMARC configured (Policy: none (monitoring)).
- PASS [Procedures] Security Inbox procedures verified (3532 bytes).

---
*Generated 2025-11-23 03:57 UTC*