## 1. Operational Environment Assumptions (From PS)
*   **ASM-OPS-001 (Connectivity):** All three clinic locations (Ang Mo Kio, Jurong, Tampines) possess reliable, always-on internet connectivity. The system is not required to function offline.
*   **ASM-OPS-002 (User Literacy):** Patients utilizing the public booking portal possess basic digital literacy and access to a personal email account for Two-Factor Authentication (2FA) and notifications.
*   **ASM-OPS-003 (Staff Readiness):** All clinic staff will undergo a mandatory 1-day training session provided by Nexus Digital Solutions before Go-Live.
*   **ASM-OPS-004 (Identity):** All doctors and staff possess active corporate email addresses (`@tricare.sg`) to be used as their primary Single Sign-On (SSO) identity.

## 2. Business Process Assumptions (From Analysis)
*   **ASM-BIZ-001 (Process Stability):** The core business processes (Registration -> Booking -> Consultation -> Payment) will remain stable for the duration of the development (9 months). Any deviation constitutes a Change Request.
*   **ASM-BIZ-002 (Legacy Data):** The client will provide a sanitized "dummy" dataset mirroring the structure of the legacy SQL/Excel records by Week 2 for migration testing (Ref: Risk R-03).
*   **ASM-BIZ-003 (Payment Provider):** Tri-Care will secure a merchant account with the designated Payment Gateway provider (e.g., Stripe/PayPal) prior to the UAT phase. Nexus is not responsible for banking compliance/KYC.

## 3. Technical & Development Assumptions
*   **ASM-TEC-001 (Hosting):** The system will be hosted on Microsoft Azure (Singapore Region) to satisfy data sovereignty requirements.
*   **ASM-TEC-002 (Hardware):** Client workstations meet the minimum specifications defined in the Analysis Report (i5 Processor, 8GB RAM, Windows 10/11). Windows 7 is assumed to be decommissioned.