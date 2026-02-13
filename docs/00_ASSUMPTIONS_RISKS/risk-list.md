# Risk Register

**Project:** Tri-Care ICMS
**Last Updated:** 13 Feb 2026
**Status:** Active Analysis

## 1. Risk Assessment Matrix
*   **Likelihood:** 1 (Rare) to 7 (Certain/Already Happening)
*   **Severity:** 1 (Negligible) to 7 (Catastrophic/Project Failure)

## 2. Customer Risks (Tri-Care's Perspective)
| ID | Risk Description | Impact | Mitigation Strategy |
| :--- | :--- | :--- | :--- |
### CR-01: Lack of Clinical Context (Safety Risk)
*   **Description:** Client fears the vendor treats the system as "just another CRUD app" and misses critical medical safety contexts (e.g., allergy alerts), potentially leading to malpractice liability.
*   **Impact:** High
*   **Mitigation:** Account Manager to enforce clinical safety reviews with Chief Medical Officer.

### CR-02: "Bait and Switch" Resourcing
*   **Description:** Client fears the proposal was pitched by senior architects, but actual coding will be done by low-skilled juniors/students.
*   **Impact:** High
*   **Mitigation:** Contract stipulates named Key Personnel (Lead Analyst, Tech Lead) cannot be swapped without approval.

### CR-03: Operational Disruption
*   **Description:** Client fears the new system is slower than manual logbooks, causing queues.
*   **Impact:** Medium
*   **Mitigation:** Strict Performance Requirement (<2s load time). Parallel run planned for Week 1 of Go-Live.

### CR-04: Hidden Costs ("Nickel-and-Diming")
*   **Description:** Client fears vendor will charge excessive "Change Request" fees for minor tweaks.
*   **Impact:** Medium
*   **Mitigation:** "Farmer" Account Manager approach; fixed-price agreement for minor UI adjustments.

### CR-05: Vendor Abandonment ("Ghosting")
*   **Description:** Client fears Nexus will deliver the software and then fail to provide frequent updates or bug fixes, leaving the clinic with unsupported software.
*   **Impact:** High
*   **Mitigation:** Contract mandates "Weekly Status Reports" (Friday 5 PM) and a 90-day Defect Liability Period post-launch.

## 3. Vendor Risks (Nexus Digital Solutions Perspective)
| ID | Risk Name | L | S | Priority | Mitigation Strategy |
| :--- | :--- | :-: | :-: | :--- | :--- |
| **VR-01** | **Scope Creep (Free Features)** | 4 | 1 | **CRITICAL** | **Strict Traceability:** Every feature must map to a PS clause. "Orphan" requests are flagged as Billable Change Requests immediately. |
| **VR-02** | **Legacy Liability (Win 7/SQL 08)** | 1 | 3 | **CRITICAL** | **Rejection:** Formally advised client to drop Windows 7. Exercised "or newer" clause to mandate SQL Server 2019 to ensure security support. |
| **VR-03** | **Data Secrecy (PDPA Block)** | 7 | 2 | **HIGH** | **Data Mocker:** If client refuses to share data, we build a Data Mocker Tool to generate synthetic HL7 records for testing. |
| **VR-04** | **Loss of "Tribal Knowledge"** | 2 | 7 | **HIGH** | **Extraction:** Treat clarification meetings as extraction sessions. Codify Madam Tan's verbal logic into the SRS immediately. |
| **VR-05** | **Subjective Metrics ("Efficient")** | 3 | 5 | **MED** | **Quantification:** Defined "Efficient" as "Page load < 2.0 seconds" and "3 clicks to book". |
| **VR-06** | **Payment Gateway Gap** | 5 | 6 | **MED** | **Scope Definition:** Defined strictly as 3rd-party API integration (Stripe). Nexus does *not* build the processor or store card details. |
| **VR-07** | **HL7 Version Mismatch** | 6 | 4 | **MED** | **Standardization:** Interpret requirement as **HL7 FHIR** standard only. External systems must adapt to our API. |

**Legend:** L = Likelihood (1-7), S = Severity (1-7