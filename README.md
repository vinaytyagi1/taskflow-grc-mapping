# TaskFlow Software — ISO/IEC 27001:2022 Control Mapping

## Project Overview
This repository contains the initial security control mapping prepared for **TaskFlow Software** as part of their ISO/IEC 27001:2022 audit readiness engagement (supported by Ezitech). 

TaskFlow's 15 existing security controls have been mapped to **ISO/IEC 27001:2022 Annex A** to establish a baseline for the upcoming formal Gap Analysis and Statement of Applicability (SoA).

## Repository Contents
* `taskflow_iso27001_mapping.csv` — Complete mapping of 15 current TaskFlow controls to ISO/IEC 27001:2022 Annex A clauses.
* `README.md` — Documentation of mapping methodology, confidence rubric, and non-clean mapping observations.

## Mapping Methodology
Each control provided by TaskFlow was evaluated using a 3-step approach:
1. **Control Intent Analysis:** Identified the core security objective of each existing practice (preventive, detective, or corrective).
2. **Annex A Alignment:** Matched each control to the most relevant clause(s) across the four ISO/IEC 27001:2022 themes—**A.5 Organizational**, **A.6 People**, **A.7 Physical**, and **A.8 Technological**. Many-to-many relationships were explicitly noted where one operational practice supports multiple ISO clauses.
3. **Auditability & Gap Flagging:** Assessed whether the control is formal, repeatable, and produces audit evidence. Controls with informal execution, partial scope, or alignment outside Annex A were flagged in the `Notes` column.

## Confidence Level Definitions
| Confidence Level | Criteria |
|---|---|
| **High** | Direct, unambiguous alignment with one or more Annex A clauses; the control is clearly defined and reasonably auditable. |
| **Medium** | Partial alignment—either the control spans multiple clauses loosely, has limited scope (e.g., excludes contractors), or lacks formal SLAs/documentation. |
| **Low** | Weak, informal, or non-clean mapping. Includes ad-hoc practices without audit trails or business controls that fall outside Annex A. |

## Controls That Do Not Map Cleanly
* **TF-13 (`#security-alerts` Slack channel):** Informal reporting lacks defined triage, severity classification, and formal incident records required by A.5.24 and A.6.8.
* **TF-14 (Verbal screen-lock reminders):** Unenforceable and non-auditable; needs to be replaced with MDM auto-lock policies and a documented remote-work policy (A.7.7 / A.7.9).
* **TF-15 (Cyber liability insurance):** Represents financial risk transfer under **Clause 6.1.3 (Risk Treatment)** rather than a technical or operational Annex A control.
