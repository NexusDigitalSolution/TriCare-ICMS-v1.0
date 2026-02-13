# Incongruous Requirements Checklist (IRC)

**Project:** Tri-Care Integrated Clinic Management System (ICMS)
**Date:** 12 Feb 2026
**Reference:** Project Specification Version 1.0

## 1. Imperative (Degree of Priority)
*   **Assessment:** Verified correct usage of modal verbs.
*   **Findings:**
    *   **Shall (9):** Mandatory features (Booking, Registration).
    *   **Must/Must Not (12):** Non-negotiable constraints (PDPA, TLS).
    *   **Should (4):** Desirable features (Post-appointment email).
    *   **Will (2):** Customer commitments (Training, Stability).
*   **Action:** No changes required. Priority definitions are clear.

## 2. Continuance (Complexity Check)
*   **Assessment:** Verified phrases like "as follows", "listed", "in particular".
*   **Findings:**
    *   **REQ-BIZ-008:** Used "details such as" without a strict list.
    *   **Action:** Decomposed into atomic sub-requirements in the SRS to reduce complexity.

## 3. Contextual (Validity & Feasibility Check)
*   **Not Testable:**
    *   **REQ-BIZ-012 (Branding):** "Incorporate Tri-Care branding."
    *   *Defect:* No guidelines provided.
    *   *Action:* Resolved by requesting "Brand Guidelines.pdf" from client.
*   **Ambiguous:**
    *   **REQ-BIZ-011 (Email):** "Send... if applicable."
    *   *Defect:* Vague trigger condition.
    *   *Action:* Clarified via stakeholder workshop (Trigger: Doctor manually flags "Follow-up Required").
*   **Unverifiable:**
    *   **REQ-BIZ-014 (Retention):** "Minimum of 7 years."
    *   *Defect:* Unverifiable without specific policy document.
    *   *Action:* Verified against MOH guidelines and interpreted as "Configurable Soft-Delete".
*   **Not Feasible / Substantively Invalid:**
    *   **REQ-TEC-001 (Legacy Liability):** "Compatible with... Windows 7."
    *   *Defect:* Windows 7 is End-of-Life (EOL). Supporting it creates critical security liability (See Risk R-02).
    *   *Action:* **Reject.** Interpret as "Windows 10/11 Only".
    *   **REQ-TEC-004 (Legacy Database):** "SQL Server 2008."
    *   *Defect:* EOL Software.
    *   *Action:* **Interpret** using the clause "(or newer)" to mandate SQL Server 2019.
*   **Suspected Incompleteness (Scope Gap):**
    *   **REQ-BIZ-017 (Payment):** "Integrate billing system."
    *   *Defect:* Implies online payment but omits "Payment Gateway" actor.
    *   *Action:* Interpreted as integration with 3rd-party Gateway (Stripe) to prevent scope creep (See Risk R-06).

---
**Summary of Analysis:**
*   **Total Requirements Reviewed:** 27
*   **Critical Defects:** 2 (Legacy Infrastructure identified as Not Feasible).
*   **Ambiguities Resolved:** 2
*   **Status:** All defects addressed via Clarification or Interpretation strategies.