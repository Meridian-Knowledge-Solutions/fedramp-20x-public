# KSI-CNA-05: Deploy effective spam, spoofing, and denial-of-service countermeasures.

## Overview

**Category:** Cloud Native Architecture
**Status:** PASS
**Last Check:** 2025-11-24 00:38

**What it validates:** Deploy effective spam, spoofing, and denial-of-service countermeasures.

**Why it matters:** Validates multi-layered DDoS protection (WAF, CloudFront, ALB, Auto Scaling) and DNS resilience. Email spam protection validated only when email services are detected (SES, MX records)

## Validation Method

1. `aws wafv2 list-web-acls --scope REGIONAL --output json`
   *Check Regional WAF for Layer 7 DDoS protection*

2. `aws wafv2 list-web-acls --scope CLOUDFRONT --region us-east-1 --output json`
   *Validate CloudFront WAF for edge DDoS protection*

3. `aws cloudfront list-distributions --output json`
   *Check CloudFront distributions for global DDoS mitigation*

4. `aws elbv2 describe-load-balancers --output json`
   *Validate Multi-AZ load balancers for service resilience*

5. `aws autoscaling describe-auto-scaling-groups --output json`
   *Check auto-scaling for capacity-based DDoS mitigation*

6. `aws route53 list-hosted-zones --output json`
   *List ALL Route53 hosted zones for DNS DDoS protection analysis*

7. `aws cloudwatch describe-alarms --output json`
   *Check CloudWatch alarms for DDoS detection and alerting*

8. `aws route53 list-hosted-zones --output json | jq -r '.HostedZones[].Id' | xargs -I {} aws route53 list-resource-record-sets --hosted-zone-id {} --max-items 100 --output json | jq -s '.' || echo '[]'`
   *Get DNS records for ALL hosted zones - validates SPF/DMARC/DKIM email authentication across all domains*

9. `aws sesv2 list-email-identities --output json || echo '{"EmailIdentities": []}'`
   *Detect email services to determine spam protection applicability*

## Latest Results

PASS Excellent 13/14 (93%): PASS [DDoS] AWS Shield Standard active.
- PASS [DDoS] Application Layer: 1 WAF ACL(s) active (meridian-waf-acl).
- PASS [DDoS] Resilience: 1 Multi-AZ Load Balancer(s).
- INFO [DDoS] No Route53 zones found.
- PASS [Spam] SES: 2 verified identity(ies).
- INFO [Spam] SES active, assuming external DNS compliance.

---
*Generated 2025-11-24 00:48 UTC*