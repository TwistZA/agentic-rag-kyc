# FICA Guardian — KYC Compliance Verification Report

**Report Generated:** 2026-04-01 17:02:14  
**Reference Date:** 2026-03-25  
**Regulatory Framework:** FICA (Act 38 of 2001), FATF Recommendations  
**Clients Processed:** 1  

---

## Executive Summary

| Client | ID Type      | Final Verdict  | Risk Level | Recommended Action |
|:------:|:-------------|:---------------|:-----------|:-------------------|
| 005 | Smart Id | REJECTED | HIGH | Reject application due to lack of valid physical proof of re... |

---

## Detailed Client Reports

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