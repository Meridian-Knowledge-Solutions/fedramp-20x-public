# KSI Documentation Index

This directory contains documentation for all Key Security Indicators (KSIs).

## Change Management

- [PASS] [KSI-CMT-01](KSI-CMT-01.md): Log and monitor modifications to the cloud service offering.
- [PASS] [KSI-CMT-02](KSI-CMT-02.md): Execute changes though redeployment of version controlled immutable resources rather than direct modification wherever possible
- [PASS] [KSI-CMT-03](KSI-CMT-03.md): Automate persistent testing and validation of changes throughout deployment.
- [FAIL] [KSI-CMT-04](KSI-CMT-04.md): Always follow a documented change management procedure.
- [PENDING] [KSI-CMT-05](KSI-CMT-05.md): Evaluate risk and potential impact of any change (Superseded by KSI-AFR-05)

## Cloud Native Architecture

- [PASS] [KSI-CNA-01](KSI-CNA-01.md): Configure all machine-based information resources to limit inbound and outbound network traffic.
- [PASS] [KSI-CNA-02](KSI-CNA-02.md): Design systems to minimize the attack surface and minimize lateral movement if compromised.
- [PASS] [KSI-CNA-03](KSI-CNA-03.md): Use logical networking and related capabilities to enforce traffic flow controls.
- [PASS] [KSI-CNA-04](KSI-CNA-04.md): Use immutable infrastructure with strictly defined functionality and privileges by default.
- [PASS] [KSI-CNA-05](KSI-CNA-05.md): Deploy effective spam, spoofing, and denial-of-service countermeasures.
- [PASS] [KSI-CNA-06](KSI-CNA-06.md): Design systems for high availability and rapid recovery.
- [PASS] [KSI-CNA-07](KSI-CNA-07.md): Maximize use of managed services and cloud resources
- [PASS] [KSI-CNA-08](KSI-CNA-08.md): Use automated services to persistently assess the security posture of all machine-based information resources and automatically enforce their intended operational state.

## Cybersecurity Education

- [PASS] [KSI-CED-01](KSI-CED-01.md): Require and monitor the effectiveness of training given to all employees on policies, procedures, and security-related topics.
- [PASS] [KSI-CED-02](KSI-CED-02.md): Require and monitor the effectiveness of role-specific training for high risk roles, including at least roles with privileged access.
- [FAIL] [KSI-CED-03](KSI-CED-03.md): Require and monitor the effectiveness of role-specific training provided to development and engineering staff that covers best practices for delivering secure software.
- [FAIL] [KSI-CED-04](KSI-CED-04.md): Require and monitor the effectiveness of role-specific training to staff involved with incident response or disaster recovery.

## Identity and Access Management

- [PASS] [KSI-IAM-01](KSI-IAM-01.md): Enforce multi-factor authentication (MFA) using methods that are difficult to intercept or impersonate (phishing-resistant MFA) for all user authentication.
- [PASS] [KSI-IAM-02](KSI-IAM-02.md): Use secure passwordless methods for user authentication and authorization when feasible, otherwise enforce strong passwords with MFA.
- [PASS] [KSI-IAM-03](KSI-IAM-03.md): Enforce appropriately secure authentication methods for non-user accounts and services.
- [PASS] [KSI-IAM-04](KSI-IAM-04.md): Require a centralized identity management system.
- [PASS] [KSI-IAM-05](KSI-IAM-05.md): Require phishing-resistant MFA for all user authentication to the cloud service offering and all customer information resources.
- [PASS] [KSI-IAM-06](KSI-IAM-06.md): Automatically disable or otherwise secure accounts with privileged access in response to suspicious activity
- [PASS] [KSI-IAM-07](KSI-IAM-07.md): Securely manage the lifecycle and privileges of all accounts, roles, and groups, using automation.

## Incident Reporting

- [PASS] [KSI-INR-01](KSI-INR-01.md): Always follow a documented incident response procedure.
- [PASS] [KSI-INR-02](KSI-INR-02.md): Maintain a log of incidents and periodically review past incidents for patterns or vulnerabilities.
- [PASS] [KSI-INR-03](KSI-INR-03.md): Generate after action reports and regularly incorporate lessons learned into operations.

## Monitoring, Logging, and Auditing

- [PASS] [KSI-MLA-01](KSI-MLA-01.md): Log all activity on all information resources supporting the cloud service offering to a protected audit log in at least one location.
- [PASS] [KSI-MLA-02](KSI-MLA-02.md): Regularly review and audit logs.
- [PENDING] [KSI-MLA-03](KSI-MLA-03.md): Rapidly detect and remediate or mitigate vulnerabilities (Superseded by KSI-AFR-04)
- [PASS] [KSI-MLA-05](KSI-MLA-05.md): Perform Infrastructure as Code and configuration evaluation and testing.
- [PASS] [KSI-MLA-07](KSI-MLA-07.md): Maintain a list of information resources and event types that will be monitored, logged, and audited, then do so.
- [PASS] [KSI-MLA-08](KSI-MLA-08.md): Use a least-privileged, role and attribute-based, and just-in-time access authorization model for access to log data based on organizationally defined data sensitivity.

## Other

- [PASS] [KSI-AFR-01](KSI-AFR-01.md): Apply the FedRAMP Minimum Assessment Standard (MAS) to identify and document the scope of the cloud service offering to be assessed for FedRAMP authorization and persistently address all related requirements and recommendations.
- [PASS] [KSI-AFR-02](KSI-AFR-02.md): Set security goals for the cloud service offering based on FedRAMP 20x Phase Two Key Security Indicators (KSIs - you are here), develop automated validation of status and progress to the greatest extent possible, and persistently address all related requirements and recommendations.
- [PASS] [KSI-AFR-03](KSI-AFR-03.md): Determine how authorization data will be shared with all necessary parties in alignment with the FedRAMP Authorization Data Sharing (ADS) standard and persistently address all related requirements and recommendations.
- [PASS] [KSI-AFR-04](KSI-AFR-04.md): Document the vulnerability detection and vulnerability response methodology used within the cloud service offering in alignment with the FedRAMP Vulnerability Detection and Response (VDR) standard and persistently address all related requirements and recommendations.
- [FAIL] [KSI-AFR-05](KSI-AFR-05.md): Verify SCN procedures are documented and active change tracking is visible via GitHub Issues.
- [PASS] [KSI-AFR-06](KSI-AFR-06.md): Maintain a plan and process for providing Ongoing Authorization Reports and Quarterly Reviews for all necessary parties in alignment with the FedRAMP Collaborative Continuous Monitoring (CCM) standard and persistently address all related requirements and recommendations.
- [PASS] [KSI-AFR-07](KSI-AFR-07.md): Document the secure configuration baseline for the cloud service offering.
- [PASS] [KSI-AFR-08](KSI-AFR-08.md): Operate a secure inbox to receive critical communication from FedRAMP and other government entities in alignment with FedRAMP Security Inbox (FSI) requirements and persistently address all related requirements and recommendations.
- [FAIL] [KSI-AFR-09](KSI-AFR-09.md): Persistently validate security posture using automated pipelines.
- [PASS] [KSI-AFR-10](KSI-AFR-10.md): Integrate FedRAMP's Incident Communications Procedures (ICP) into incident response procedures and infrastructure.
- [PASS] [KSI-AFR-11](KSI-AFR-11.md): Ensure that cryptographic modules used to protect potentially sensitive federal customer data are selected and used in alignment with the FedRAMP 20x Using Cryptographic Modules (UCM) policy and persistently address all related requirements and recommendations.

## Policy and Inventory

- [PASS] [KSI-PIY-01](KSI-PIY-01.md): Use authoritative sources to automatically maintain real-time inventories of all information resources.
- [PASS] [KSI-PIY-02](KSI-PIY-02.md): Document the security objectives and requirements for each information resource or set of information resources.
- [PASS] [KSI-PIY-03](KSI-PIY-03.md): Maintain a vulnerability disclosure program.
- [PASS] [KSI-PIY-04](KSI-PIY-04.md): Monitor the effectiveness of building security and privacy considerations into the Software Development Lifecycle and aligning with CISA Secure By Design principles.
- [PASS] [KSI-PIY-05](KSI-PIY-05.md): Document methods used to evaluate information resource implementations.
- [PASS] [KSI-PIY-06](KSI-PIY-06.md): Monitor the effectiveness of the organization's investments in achieving security objectives.
- [PASS] [KSI-PIY-07](KSI-PIY-07.md): Document risk management decisions for software supply chain security.
- [FAIL] [KSI-PIY-08](KSI-PIY-08.md): Measure executive support via active budgetary controls and financial commitment.

## Recovery Planning

- [PASS] [KSI-RPL-01](KSI-RPL-01.md): Define Recovery Time Objectives (RTO) and Recovery Point Objectives (RPO).
- [PASS] [KSI-RPL-02](KSI-RPL-02.md): Develop and maintain a recovery plan that aligns with the defined recovery objectives.
- [PASS] [KSI-RPL-03](KSI-RPL-03.md): Regularly test the recovery planning capability by performing disaster recovery tests at least annually.
- [PASS] [KSI-RPL-04](KSI-RPL-04.md): Regularly test the capability to recover from incidents and contingencies.

## Service Configuration

- [PASS] [KSI-SVC-01](KSI-SVC-01.md): Implement improvements based on persistent evaluation of information resources for opportunities to improve security.
- [PASS] [KSI-SVC-02](KSI-SVC-02.md): Encrypt or otherwise secure network traffic.
- [PENDING] [KSI-SVC-03](KSI-SVC-03.md): Encrypt data at rest
- [PASS] [KSI-SVC-04](KSI-SVC-04.md): Manage configuration of machine-based information resources using automation.
- [PASS] [KSI-SVC-05](KSI-SVC-05.md): Use cryptographic methods to validate the integrity of machine-based information resources.
- [PASS] [KSI-SVC-06](KSI-SVC-06.md): Automate management, protection, and regular rotation of digital keys, certificates, and other secrets.
- [PASS] [KSI-SVC-07](KSI-SVC-07.md): Use a consistent, risk-informed approach for applying security patches.
- [PASS] [KSI-SVC-08](KSI-SVC-08.md): Do not introduce or leave behind residual elements that could negatively affect confidentiality, integrity, or availability of federal customer data during operations.
- [PASS] [KSI-SVC-09](KSI-SVC-09.md): Persistently validate the authenticity and integrity of communications between machine-based information resources using automation.
- [PASS] [KSI-SVC-10](KSI-SVC-10.md): Remove unwanted federal customer data promptly when requested by an agency in alignment with customer agreements, including from backups if appropriate.

## Third-Party Information Resources

- [PENDING] [KSI-TPR-01](KSI-TPR-01.md): Document the cloud service provider (CSP) in the system security policy
- [PASS] [KSI-TPR-03](KSI-TPR-03.md): Identify and prioritize mitigation of potential supply chain risks.
- [PASS] [KSI-TPR-04](KSI-TPR-04.md): Automatically monitor third party software information resources for upstream vulnerabilities using mechanisms that may include contractual notification requirements or active monitoring services.

## Summary

- **Total KSIs:** 69
- **Passing:** 59
- **Failing:** 6
- **Not Tested:** 4

---
<<<<<<< Updated upstream
*Generated 2025-11-24 00:48 UTC*
=======
*Generated 2025-11-24 01:10 UTC*
>>>>>>> Stashed changes
