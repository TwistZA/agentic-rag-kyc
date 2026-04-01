# FICA Guardian — KYC Compliance Verification Report

**Report Generated:** 2026-04-01 14:04:33  
**Reference Date:** 2026-03-25  
**Regulatory Framework:** FICA (Act 38 of 2001), FATF Recommendations  
**Clients Processed:** 1  

---

## Executive Summary

| Client | ID Type      | Final Verdict  | Risk Level | Recommended Action |
|:------:|:-------------|:---------------|:-----------|:-------------------|
| 002 | Green Book | REJECTED | HIGH | Request a current Proof of Residence document (dated within ... |

---

## Detailed Client Reports

### Client 002

| Field              | Value |
|:-------------------|:------|
| **Final Verdict**  | REJECTED |
| **Risk Level**     | HIGH |
| **ID Type**        | Green Book |
| **Audit Timestamp**| 2026-03-25T10:00:00Z |

**Gate Results:**

**Gate 1: Structural Identity Integrity** — PASS
  - ID format valid (Luhn warning recorded).
  - ID number matches KYC form.
  - Date of birth consistent.

**Gate 2: Residency & Recency** — FAIL
  - Proof of Residence (bank statement) is 175 days old, exceeding the 90-day currency requirement.
  - Physical address verified.
  - Address matches KYC form.
  - Bank branch code could not be validated.

**Gate 3: Database Risk Screening** — PASS
  - No sanctions hit.
  - No PEP registry hit.

**Recommended Action:** Request a current Proof of Residence document (dated within the last 90 days).

---