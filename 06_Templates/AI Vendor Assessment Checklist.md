---
document-id: MC-VEN-AI-001
framework: "NIST AI RMF 1.0 - GOVERN 1.4, MAP 3.5, MEASURE 2.7"
regulatory: "HIPAA 45 CFR 164.308(b)"
version: 1.0
status: draft
instructions: "Complete for every AI vendor before authorization. Must be reviewed by IT Security and Privacy Officer. BAA is required for any system processing PHI before assessment can be marked complete."
---

# MC-VEN-AI-001 - AI Vendor Assessment Checklist

**MedCore Health Systems**
*IT Security / Privacy Officer Use - One per vendor*

---

## Vendor Information

| Field                       | Response                          |
| --------------------------- | --------------------------------- |
| Vendor name                 |                                   |
| AI product name and version |                                   |
| Assessment date             |                                   |
| Assessed by                 |                                   |
| Intake form reference       | MC-FORM-AI-001 - Submission date: |
| Risk tier (from intake)     |                                   |

---

## Section A -- Legal and Contractual

| #    | Requirement                                                                   | Status                | Notes |
| ---- | ----------------------------------------------------------------------------- | --------------------- | ----- |
| A-01 | Business Associate Agreement (BAA) available and reviewed by Legal            | Pass / Fail / N/A     |       |
| A-02 | BAA covers all PHI processing activities for this use case                    | Pass / Fail / N/A     |       |
| A-03 | Vendor data processing agreement (DPA) reviewed                               | Pass / Fail / N/A     |       |
| A-04 | Vendor ToS does not permit use of MedCore inputs to train models              | Pass / Fail / Unknown |       |
| A-05 | Data residency requirements met (US-based for HIPAA PHI)                      | Pass / Fail / Unknown |       |
| A-06 | Vendor breach notification obligations defined in BAA (60-day HIPAA timeline) | Pass / Fail           |       |
| A-07 | Vendor liability and indemnification terms reviewed by Legal                  | Pass / Fail           |       |
| A-08 | Termination and data return/destruction provisions in contract                | Pass / Fail           |       |

**Section A result:** Pass (all A-01 through A-08 Pass) / Fail / Conditional

---

## Section B - Security Posture

| #    | Requirement                                                       | Status                | Notes |
| ---- | ----------------------------------------------------------------- | --------------------- | ----- |
| B-01 | SOC 2 Type II report obtained and reviewed (within 12 months)     | Pass / Fail / Pending |       |
| B-02 | Vendor publishes a security whitepaper or trust center            | Pass / Fail           |       |
| B-03 | Data encryption in transit (TLS 1.2+) confirmed                   | Pass / Fail           |       |
| B-04 | Data encryption at rest confirmed                                 | Pass / Fail           |       |
| B-05 | Multi-factor authentication available for admin access            | Pass / Fail           |       |
| B-06 | Access control: role-based access for MedCore staff               | Pass / Fail           |       |
| B-07 | Vendor penetration testing conducted annually (evidence provided) | Pass / Fail / Unknown |       |
| B-08 | Vendor vulnerability disclosure / CVE program exists              | Pass / Fail / Unknown |       |
| B-09 | Vendor incident response process documented and shared            | Pass / Fail           |       |
| B-10 | Vendor subprocessor list reviewed (who else touches MedCore data) | Pass / Fail           |       |

**Section B result:** Pass / Fail / Conditional

---

## Section C - AI-Specific Provenance and Safety

| #    | Requirement                                                                           | Status                     | Notes |
| ---- | ------------------------------------------------------------------------------------- | -------------------------- | ----- |
| C-01 | Model card or equivalent documentation available                                      | Pass / Fail                |       |
| C-02 | Training data sources disclosed or described                                          | Pass / Fail / Unknown      |       |
| C-03 | Known limitations and failure modes documented                                        | Pass / Fail                |       |
| C-04 | Bias and fairness testing documented                                                  | Pass / Fail / Unknown      |       |
| C-05 | Vendor discloses model update / retraining cadence                                    | Pass / Fail / Unknown      |       |
| C-06 | Vendor provides notification of significant model changes                             | Pass / Fail - in contract? |       |
| C-07 | Vendor provides accuracy benchmarks relevant to MedCore use case                      | Pass / Fail                |       |
| C-08 | Vendor documents adversarial testing / red team methodology                           | Pass / Fail / Unknown      |       |
| C-09 | Vendor has AI ethics or responsible AI policy published                               | Pass / Fail                |       |
| C-10 | HITL is technically feasible with this system (outputs can be reviewed before action) | Pass / Fail                |       |

**Section C result:** Pass / Fail / Conditional

---

## Section D - HIPAA Compliance Verification

| # | Requirement | Status | Notes |
|---|-------------|--------|-------|
| D-01 | Vendor explicitly represents HIPAA compliance for covered entity use | Pass / Fail | |
| D-02 | Vendor's PHI handling documented (where stored, how long retained) | Pass / Fail | |
| D-03 | Vendor data retention and deletion policy documented | Pass / Fail | |
| D-04 | Audit logging of PHI access available to MedCore | Pass / Fail | |
| D-05 | Vendor workforce trained on PHI handling | Pass / Fail / Unknown | |
| D-06 | Vendor provides right to audit (or accepts third-party audit) | Pass / Fail | |

**Section D result:** Pass / Fail / Conditional

---

## Section E - Operational Requirements

| # | Requirement | Status | Notes |
|---|-------------|--------|-------|
| E-01 | Uptime SLA documented and acceptable for clinical use | Pass / Fail / N/A | |
| E-02 | Vendor support SLA documented | Pass / Fail | |
| E-03 | Disaster recovery / business continuity plan documented | Pass / Fail | |
| E-04 | Exit / migration plan feasible if vendor relationship ends | Pass / Fail | |
| E-05 | API documentation complete for integration with MedCore systems | Pass / Fail / N/A | |

**Section E result:** Pass / Fail / Conditional

---

## Overall Assessment

| Section                    | Result | Critical Gaps |
| -------------------------- | ------ | ------------- |
| A - Legal / Contractual    |        |               |
| B - Security Posture       |        |               |
| C - AI Provenance / Safety |        |               |
| D - HIPAA Compliance       |        |               |
| E - Operational            |        |               |

**Overall recommendation:**

- [ ] **Approve** - All sections Pass or Conditional with acceptable gaps; BAA in place
- [ ] **Conditional Approval** - Minor gaps documented; mitigation plan required before authorization
- [ ] **Reject** - One or more critical gaps (BAA unavailable, Section D failures, HITL not feasible)

**Critical gaps requiring remediation (if any):**

---

**IT Security reviewer:** _________________________ **Date:** _____________

**Privacy Officer reviewer (required for PHI-processing systems):** _________________________ **Date:** _____________

**CISO sign-off:** _________________________ **Date:** _____________

---

*MedCore Health Systems - Internal Use Only*
*MC-VEN-AI-001 v1.0 - AI Vendor Assessment Checklist*

[AI Intake Form](AI%20System%20Intake%20Form.md) | [AI Inventory](AI%20Use%20Case%20Inventory.md) | [Project Overview](AI%20Change%20Mgmt%20RMF%20-%20(Overview).md)
