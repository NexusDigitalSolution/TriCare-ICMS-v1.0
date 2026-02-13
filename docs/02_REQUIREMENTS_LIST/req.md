# Consolidated Requirements Specification (Categorized)

**Reference:** ISO/IEEE 29148 Standard
**Source:** Analyzed Project Specification (TC-PS-2026-001)
**Revision:** Post-Analysis Interpretation

## 1. Functional Requirements
*Core system capabilities and user interactions.*

*   **SYS-FCN-001 (Registration):** The system shall provide a web interface for new patient registration, capturing NRIC, contact details, and medical history. (Ref: REQ-BIZ-007)
*   **SYS-FCN-002 (Booking):** The system shall allow patients to book appointments by filtering for Location (Ang Mo Kio, Jurong, Tampines), Specialty/Doctor, and Available Time Slots. (Ref: REQ-BIZ-008)
*   **SYS-FCN-003 (Schedule Mgmt):** The system shall provide a dashboard for clinic staff to view, modify, and cancel patient and doctor schedules in real-time. (Ref: REQ-BIZ-009)
*   **SYS-FCN-004 (Email Logic):** The system shall trigger a post-appointment email **only when** the "Follow-up Required" checkbox is manually selected by the Doctor. The email shall include a visit summary and feedback link. (Ref: REQ-BIZ-011 - *Clarified*)
*   **SYS-FCN-005 (Notifications):** The system shall automatically send appointment confirmations and reminders via the Email Gateway. (Ref: REQ-BIZ-015)

## 2. Business Rules & Compliance
*Constraints on data handling and logic.*

*   **SYS-BIZ-001 (PDPA):** The system must mask NRICs in all public displays and encrypt contact details at rest to comply with the Personal Data Protection Act (Singapore). (Ref: REQ-BIZ-018, REQ-BIZ-013)
*   **SYS-BIZ-002 (Data Sovereignty):** All patient data must be hosted on servers physically located within Singapore. (Ref: REQ-BIZ-019)
*   **SYS-BIZ-003 (Retention):** The system shall implement a "Soft Delete" mechanism for records, retaining data for a minimum of 7 years with an option to archive/export. (Ref: REQ-BIZ-014 - *Interpreted*)
*   **SYS-BIZ-004 (Audit):** The system must log all user actions (Create, Read, Update, Delete) regarding patient records into an immutable Audit Trail. (Ref: REQ-BIZ-010)

## 3. External Interface Requirements
*Connections to third-party systems.*

*   **SYS-INT-001 (Billing):** The system shall integrate with the existing Billing System API to push consultation fees and retrieve payment status. (Ref: REQ-BIZ-017)
*   **SYS-INT-002 (Payment Gateway):** The system shall interface with a 3rd-party Payment Gateway (e.g., Stripe) to facilitate secure credit card transactions. **Note:** The system shall *not* store raw credit card numbers. (Ref: Risk R-06 Scope Gap)
*   **SYS-INT-003 (HL7 Data):** The system shall accept patient record imports formatted as **HL7 FHIR** messages. (Ref: REQ-TEC-006 - *Interpreted*)

## 4. Performance & Technical Requirements
*System qualities and infrastructure.*

*   **SYS-PER-001 (Load Time):** The application pages must load in < 3.0 seconds on standard clinic workstations (i5/8GB RAM). (Ref: REQ-TEC-003 - *Quantified*)
*   **SYS-TEC-001 (OS Compatibility):** The web application must be fully functional on Windows 10 and Windows 11 using modern browsers (Edge/Chrome). **Note:** Windows 7 support is explicitly deprecated due to security liability. (Ref: REQ-TEC-001 - *Interpreted*)
*   **SYS-TEC-002 (Database):** The backend shall utilize Microsoft SQL Server 2019 or newer to ensure long-term support. (Ref: REQ-TEC-004 - *Interpreted*)
*   **SYS-TEC-003 (Framework):** The application shall be built using the ASP.NET Core framework. (Ref: REQ-TEC-002)

## 5. Security Requirements
*   **SYS-SEC-001 (Encryption):** All data in transit must be encrypted using TLS 1.2 or higher. (Ref: REQ-TEC-008, REQ-TEC-007)
*   **SYS-SEC-002 (Migration):** The system shall include scripts to migrate active patient records (last 24 months) from the legacy system. Older records will be archived. (Ref: REQ-BIZ-016 - *Clarified*)