# TaskFlow Software — ISO/IEC 27001:2022 Gap Analysis Report

**Prepared by:** Junior GRC Analyst, Ezitech  
**Client:** TaskFlow Software  
**Date:** November 2026  
**Standard:** ISO/IEC 27001:2022 (Annex A)  
**Baseline:** `taskflow_iso27001_mapping.csv` (15 existing controls)

## 1. Executive Summary
An assessment of TaskFlow Software's 15 existing security controls against ISO/IEC 27001:2022 Annex A identified **7 priority gaps**—6 weak or partial implementations from the current control set and 1 missing foundational control (Supplier Security). While core technical controls (SSO/MFA, encryption, automated backups, and environment separation) are strong, formal governance, incident response workflows, and remediation SLAs must be established prior to the Stage 1 certification audit.

## 2. Identified Gaps & Remediation Plan

| Gap ID | Linked Control | ISO 27001 Clause | Gap Description | Risk Priority | Proposed Remediation Action | Owner | Target Timeline |
|---|---|---|---|---|---|---|---|
| **GAP-01** | TF-13 | A.5.24, A.6.8 | Security incidents are reported informally in a `#security-alerts` Slack channel with no triage, severity tiers, or formal incident log. | **Critical** | Implement a formal Incident Response Plan (IRP) with P1–P4 severity definitions, escalation paths, and a dedicated Jira/PagerDuty incident log. | Engineering Lead / SecOps | 30 days |
| **GAP-02** | TF-10 | A.8.8 | Monthly Trivy container scans run automatically, but patching is ad-hoc with no defined remediation SLAs. | **Critical** | Establish a Vulnerability Management Policy enforcing remediation SLAs (Critical: 7 days, High: 30 days, Medium: 90 days) tracked via Jira tickets. | DevOps Lead | 30 days |
| **GAP-03** | Missing | A.5.19, A.5.22 | No documented vendor risk assessment process exists for critical SaaS/cloud subprocessors (AWS, Datadog, Google Workspace). | **High** | Create a Vendor Inventory and perform annual security reviews (collecting SOC 2 Type II or ISO 27001 certificates) for all Tier-1 suppliers. | GRC / Operations | 45 days |
| **GAP-04** | TF-14 | A.7.7, A.7.9 | Clear-screen and remote-work security rely on verbal reminders at all-hands meetings; not enforceable or auditable. | **High** | Publish a formal Remote Work & Clear Screen Policy and enforce a 5-minute automatic screen lock via MDM (Jamf/Intune) on all laptops. | IT Admin | 45 days |
| **GAP-05** | TF-09 | A.8.28 | GitHub PR reviews check general code quality, but lack documented secure coding standards or security review checklists. | **Medium** | Adopt an OWASP-aligned Secure Coding Standard and add a mandatory security checklist to the GitHub Pull Request template. | Engineering Lead | 60 days |
| **GAP-06** | TF-04 | A.6.3 | Security awareness training is delivered only during new-hire onboarding; no annual refreshers or completion tracking exist. | **Medium** | Deploy an annual security awareness training program via an LMS with mandatory completion tracking and signed acknowledgments. | HR / People Ops | 60 days |
| **GAP-07** | TF-12 | A.6.1 | Pre-employment background checks apply only to full-time engineers, excluding contractors and non-engineering staff. | **Medium** | Expand the HR Screening Policy to require background checks for all full-time employees and contractors with access to company systems. | HR / People Ops | 60 days |

## 3. Remediation Priorities
1. **Immediate (0–30 Days):** Close Critical operational gaps (**GAP-01** Incident Response and **GAP-02** Vulnerability SLAs) to reduce active breach exposure.
2. **Short-Term (31–45 Days):** Formalize third-party risk (**GAP-03**) and enforce technical endpoint lock policies via MDM (**GAP-04**).
3. **Pre-Audit (46–60 Days):** Standardize secure coding checklists (**GAP-05**), annual training (**GAP-06**), and universal background screening (**GAP-07**), then collect 90 days of operating evidence for the Stage 2 audit.

## 4. Linked Evidence Pack
Sample audit evidence for TaskFlow's 5 most critical existing controls is stored in the `evidence-pack/` directory:
* **TF-01:** `evidence-pack/TF-01_A5.17_A8.5_Password_MFA_Policy.md`
* **TF-02:** `evidence-pack/TF-02_A8.13_AWS_Backup_Restore_Log.md`
* **TF-03:** `evidence-pack/TF-03_A5.18_A8.2_Quarterly_Access_Review_Log.md`
* **TF-05:** `evidence-pack/TF-05_A5.18_A6.5_Offboarding_Revocation_Log.md`
* **TF-11:** `evidence-pack/TF-11_A8.15_A8.16_Logging_Monitoring_Evidence.md`
