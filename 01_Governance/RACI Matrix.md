---
document-id: MC-GOV-AI-001
framework: NIST AI RMF 1.0 - GOVERN Function
regulatory: HIPAA, HITECH
version: 1
status: draft
---

# MC-GOV-AI-001 - AI Governance RACI Matrix

**MedCore Health Systems**
*Internal Governance Document - Version 1.0*

**How to read this matrix**

**R** = Responsible (does the work) | **A** = Accountable (owns the outcome, approves) | **C** = Consulted (input required before action) | **I** = Informed (notified after action)
Each activity must have exactly one **A**. Multiple **R** is acceptable. If a cell is blank, that role has no defined involvement.

---

## Role Definitions

| Abbreviation | Role | Person/Team |
|---|---|---|
| CISO | Chief Information Security Officer | AI Governance Committee Chair |
| PO | Privacy Officer | HIPAA compliance lead |
| CMO | Chief Medical Officer | Clinical oversight |
| CFO | Chief Financial Officer | Budget authority |
| ITS | IT Security Team | Technical implementation |
| DM | Department Managers | Frontline staff oversight |
| HR | Human Resources | Training and workforce |
| STAFF | All MedCore Employees | End users |
| LEGAL | Legal Counsel | Regulatory and contract review |
| VENDOR | AI Vendors / Business Associates | Third-party system providers |

---

## GOVERN - Policy and Accountability

| Activity | CISO | PO | CMO | CFO | ITS | DM | HR | STAFF | LEGAL | VENDOR |
|----------|------|----|-----|-----|-----|----|----|-------|-------|--------|
| Own and maintain AI Governance Charter | A/R | C | C | I | C | I | I | | C | |
| Own and maintain AI AUP (MC-POL-AI-001) | A | R | C | I | C | C | C | I | C | |
| Approve exceptions to AI AUP | A | C | C | | I | | | | C | |
| Maintain AI governance document hierarchy | A/R | C | | | I | | | | | |
| Conduct annual AI governance review | A | R | C | I | R | I | I | | C | |
| Brief executive leadership / board on AI risk | A/R | C | C | C | | | | | | |
| Define AI risk tier classifications | A | C | C | | R | | | | C | |

---

## MAP - Inventory and Risk Context

| Activity | CISO | PO | CMO | CFO | ITS | DM | HR | STAFF | LEGAL | VENDOR |
|----------|------|----|-----|-----|-----|----|----|-------|-------|--------|
| Maintain AI Use Case Inventory (MC-INV-AI-001) | A | C | C | | R | C | | | | I |
| Conduct Shadow AI Discovery assessments | A | I | I | | R | C | | I | | |
| Receive and triage AI Anomaly Reports | A | C | | | R | I | | | | |
| Classify new AI systems by risk tier | A | C | C | | R | C | | | C | I |
| Maintain organizational AI risk context document | A | C | C | C | R | I | | | | |
| Identify PHI data flows through AI systems | A | R | C | | C | C | | | | C |

---

## MEASURE - Risk Assessment

| Activity | CISO | PO | CMO | CFO | ITS | DM | HR | STAFF | LEGAL | VENDOR |
|----------|------|----|-----|-----|-----|----|----|-------|-------|--------|
| Maintain AI Risk Register (MC-RISK-AI-001) | A | C | C | | R | I | | | | |
| Conduct AI vendor risk assessments (MC-VEN-AI-001) | A | C | | | R | | | | C | C |
| Review and sign Business Associate Agreements | C | A | | | C | | | | R | R |
| Perform red team / prompt injection testing | A | I | | | R | | | | | |
| Monitor authorized AI systems for anomalies | A | I | C | | R | I | | I | | I |
| Track AI system model drift | A | I | C | | R | I | | | | C |
| Maintain NIST AI RMF x HIPAA Crosswalk | A | R | | | C | | | | C | |

---

## MANAGE - Risk Treatment and Incident Response

| Activity | CISO | PO | CMO | CFO | ITS | DM | HR | STAFF | LEGAL | VENDOR |
|----------|------|----|-----|-----|-----|----|----|-------|-------|--------|
| Approve new AI system deployment | A | C | C | C | C | | | | C | |
| Process AI System Intake Forms (MC-FORM-AI-001) | A | C | | | R | | | | | |
| Suspend unauthorized AI system use | A | I | I | | R | I | | I | | |
| Respond to AI security incidents (MC-IRP-AI-001) | A | R | C | I | R | I | | I | C | C |
| Notify HHS OCR of AI-related PHI breach | C | A | | | | | | | R | |
| Manage staff AI policy violations | C | C | C | | I | A | R | | | |
| Issue AI vendor corrective action notices | A | C | | | R | | | | C | |
| Decommission retired AI systems | A | I | C | | R | C | | | | C |

---

## TRAINING - Workforce

| Activity | CISO | PO | CMO | CFO | ITS | DM | HR | STAFF | LEGAL | VENDOR |
|----------|------|----|-----|-----|-----|----|----|-------|-------|--------|
| Design AI literacy training curriculum | C | C | C | | C | I | A/R | | | |
| Deliver annual AI security awareness training | C | C | | | | C | A/R | R | | |
| Track training completion and compliance | I | C | | | | C | A/R | | | |
| Deliver role-specific AI clinical training | C | C | A | | | R | R | | | |
| Maintain Workforce Transition Plan | C | I | C | C | | C | A/R | | | |

---

## Escalation RACI

| Scenario | Who Detects | First Escalation | Accountable for Resolution |
|----------|-------------|-----------------|--------------------------|
| Staff using ChatGPT with PHI | STAFF / DM | ITS (same day) | CISO |
| AI system producing erroneous clinical output | STAFF / Clinician | CMO + ITS (immediate) | CMO + CISO |
| Vendor AI breach affecting MedCore data | VENDOR / ITS | CISO (within 4 hrs) | PO (HIPAA breach assessment) |
| Shadow AI discovery during IT audit | ITS | CISO (within 24 hrs) | CISO |
| PHI confirmed in unauthorized AI system | PO | CEO + LEGAL (within 1 hr) | PO (breach notification) |
| Regulatory inquiry from HHS OCR | LEGAL | CEO + CISO (within 2 hrs) | LEGAL + PO |

---

## Version History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | April 2026 | D'Arcy Bracken | Initial draft |

---

*MedCore Health Systems - Internal Use Only*
*MC-GOV-AI-001 v1.0 - AI Governance RACI Matrix*

[Back to Project Overview](AI%20Change%20Mgmt%20RMF%20-%20(Overview).md) | [Governance Charter](AI%20Governance%20Charter.md) | [AI AUP](AI%20Acceptable%20Use%20Policy.md)
