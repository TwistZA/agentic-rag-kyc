# FICA Guardian — KYC Compliance Verification Report

**Report Generated:** 2026-04-01 17:56:03  
**Reference Date:** 2026-03-25  
**Regulatory Framework:** FICA (Act 38 of 2001), FATF Recommendations  
**Clients Processed:** 5  

---

## Executive Summary

| Client | ID Type      | Final Verdict  | Risk Level | Recommended Action |
|:------:|:-------------|:---------------|:-----------|:-------------------|
| 001 | Smart Id | APPROVED | LOW | Proceed with account opening. |
| 002 | Green Book | REJECTED | HIGH | Request a current Proof of Residence document (dated within the last 90 days). |
| 003 | Smart Id | CRITICAL ALERT | CRITICAL | Immediate rejection due to identity tampering (Smart ID name mismatch). Flag for internal fraud investigation. |
| 004 | Smart Id | FLAG - EDD | HIGH | Perform Enhanced Due Diligence (EDD) due to PEP status. Manually verify the date of the lease agreement as it was not automatically detected. |
| 005 | Smart Id | REJECTED | HIGH | Reject application due to lack of valid physical proof of residence. Request a utility bill or bank statement showing a physical street address. |

---

## Detailed Client Reports

### Client 001

| Field              | Value |
|:-------------------|:------|
| **Final Verdict**  | APPROVED |
| **Risk Level**     | LOW |
| **ID Type**        | Smart Id |
| **Audit Timestamp**| 2026-03-25T10:00:00Z |

**Gate Results:**

**Gate 1: Structural Identity Integrity** — PASS
  - ID format valid (Luhn warning noted)
  - ID number matches KYC form
  - Smart ID barcode integrity verified
  - Date of birth consistent

**Gate 2: Residency & Recency** — PASS
  - Utility bill classified correctly
  - Document within 90-day currency window
  - Physical street address verified
  - Address matches KYC form

**Gate 3: Database Risk Screening** — PASS
  - No sanctions hit
  - No PEP registry hit
  - Bank reference check not applicable

**Recommended Action:** Proceed with account opening.

---
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
### Client 003

| Field              | Value |
|:-------------------|:------|
| **Final Verdict**  | CRITICAL ALERT |
| **Risk Level**     | CRITICAL |
| **ID Type**        | Smart Id |
| **Audit Timestamp**| 2026-03-25T10:00:00Z |

**Gate Results:**

**Gate 1: Structural Identity Integrity** — FAIL
  - ID format valid, but Luhn checksum failed (warning).
  - CRITICAL: Name mismatch on Smart ID. Front OCR name 'DOE JOHN' does not match barcode name 'GUMEDE SIPHO'. Identity tampering suspected.

**Gate 2: Residency & Recency** — PASS
  - PoR classified as utility bill.
  - PoR is within 90-day currency window.
  - Physical street address confirmed.
  - Address on form matches address on PoR.

**Gate 3: Database Risk Screening** — PASS
  - No sanctions list hits.
  - No PEP registry hits.

**Recommended Action:** Immediate rejection due to identity tampering (Smart ID name mismatch). Flag for internal fraud investigation.

---
### Client 004

| Field              | Value |
|:-------------------|:------|
| **Final Verdict**  | FLAG - EDD |
| **Risk Level**     | HIGH |
| **ID Type**        | Smart Id |
| **Audit Timestamp**| 2026-03-25T12:00:00Z |

**Gate Results:**

**Gate 1: Structural Identity Integrity** — PASS
  - ID format valid
  - Luhn checksum warning (advisory)
  - ID number matches KYC form
  - Smart ID barcode integrity check passed
  - Date of birth consistent

**Gate 2: Residency & Recency** — MANUAL_REVIEW
  - PoR classified as lease_agreement
  - PoR date not found (manual review required)
  - Physical street address confirmed
  - Address matches KYC form

**Gate 3: Database Risk Screening** — FLAG_EDD
  - No sanctions hit
  - PEP registry hit: Minister of Energy (Enhanced Due Diligence required)

**Recommended Action:** Perform Enhanced Due Diligence (EDD) due to PEP status. Manually verify the date of the lease agreement as it was not automatically detected.

---
### Client 005

| Field              | Value |
|:-------------------|:------|
| **Final Verdict**  | REJECTED |
| **Risk Level**     | HIGH |
| **ID Type**        | Smart Id |
| **Audit Timestamp**| 2026-03-25T12:00:00Z |

**Gate Results:**

**Gate 1: Structural Identity Integrity** — PASS
  - ID format valid (Luhn warning recorded)
  - ID number matches KYC form
  - Barcode integrity verified
  - DOB consistent

**Gate 2: Residency & Recency** — FAIL
  - PoR classified as SAPS affidavit
  - PoR within 90-day window
  - PoR contains only a PO Box (FICA non-compliant)
  - Address triangulation failed (KYC physical address vs PoR PO Box)

**Gate 3: Database Risk Screening** — PASS
  - No sanctions hit
  - No PEP registry hit

**Recommended Action:** Reject application due to lack of valid physical proof of residence. Request a utility bill or bank statement showing a physical street address.

---