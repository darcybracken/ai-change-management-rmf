---
document-id: MC-INV-AI-001
framework: NIST AI RMF 1.0 - MAP Function
regulatory: HIPAA, HITECH
version: 1
status: draft
---

# MC-INV-AI-001 - AI Use Case Inventory

**MedCore Health Systems**
*Internal Governance Document - Version 1.0*


**Purpose**

This inventory is the authoritative record of all AI systems in use at MedCore Health Systems, authorized and unauthorized. It is maintained by IT Security and reviewed semi-annually by the AI Governance Committee. The inventory is the MAP function foundation you cannot assess, govern, or manage AI risk you have not identified.

---

## Inventory Summary

| Metric | Count |
|--------|-------|
| Authorized systems | 1 (conditional) |
| Systems under evaluation | 2 |
| Unauthorized / Shadow AI | 1 (active, high priority) |
| Total AI systems tracked | 4 |
| Systems with signed BAA | 1 |
| Systems with PHI exposure | 3 |

---

## Authorized Systems

### AS-001 - AutoCode Billing Assistant

| Field                    | Detail                                                                                     |
| ------------------------ | ------------------------------------------------------------------------------------------ |
| **System name**          | AutoCode Billing Assistant                                                                 |
| **Vendor**               | AutoCode Medical Technologies (fictional)                                                  |
| **Version**              | 3.2.1                                                                                      |
| **System ID**            | AS-001                                                                                     |
| **Authorization status** | Conditionally Authorized                                                                   |
| **Authorization date**   | January 2026                                                                               |
| **Authorizing officer**  | CISO                                                                                       |
| **Risk tier**            | Medium                                                                                     |
| **Use case**             | AI-assisted medical billing code (ICD-10, CPT) suggestions for billing department staff    |
| **Users**                | Billing Department (~12 staff)                                                             |
| **PHI processed**        | Yes - billing records (patient name, DOB, diagnosis codes, procedure codes)                |
| **PHI classification**   | Limited - billing records only; no clinical notes, imaging, or treatment plans             |
| **Data residency**       | Vendor cloud (US-East region), BAA in place                                                |
| **BAA status**           | Signed - expires January 2028                                                              |
| **HITL requirement**     | Yes - all code suggestions reviewed and approved by billing staff before claim submission  |
| **Monitoring**           | IT Security quarterly log review                                                           |
| **Known limitations**    | Model occasionally suggests outdated ICD-10 codes; staff training on verification required |
| **Next review**          | October 2026                                                                               |
| **Document ref**         | MC-RISK-AI-001 (Risk Register entry RI-001)                                                |

---

## Systems Under Evaluation

### SE-001 - DiagnoAI Imaging Assistant

| Field                    | Detail                                                                                                                          |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------- |
| **System name**          | DiagnoAI Imaging Assistant                                                                                                      |
| **Vendor**               | DiagnoAI Inc. (fictional)                                                                                                       |
| **System ID**            | SE-001                                                                                                                          |
| **Authorization status** | Under Evaluation - not authorized for clinical use                                                                              |
| **Evaluation started**   | March 2026                                                                                                                      |
| **Risk tier**            | High                                                                                                                            |
| **Use case**             | AI-assisted analysis of diagnostic imaging (X-ray, MRI, CT) to flag findings for radiologist review                             |
| **Users (proposed)**     | Radiology and clinical staff (~8 physicians, 4 radiology techs)                                                                 |
| **PHI processed**        | Yes - imaging data with patient identifiers, highest sensitivity class                                                          |
| **BAA status**           | Under negotiation - NOT signed, system must not be used with real patient data until BAA is executed                            |
| **HITL requirement**     | Mandatory - physician sign-off required on all AI-flagged findings before clinical action                                       |
| **Evaluation criteria**  | Vendor security assessment (MC-VEN-AI-001), BAA execution, pilot with de-identified data, CMO clinical validation, AGC approval |
| **Current status**       | Vendor assessment in progress. De-identified pilot pending CMO approval.                                                        |
| **Blocking issues**      | BAA not yet signed, no de-identified pilot dataset prepared                                                                     |
| **Estimated approval**   | Q3 2026 if assessment and pilot complete                                                                                        |
| **Document ref**         | MC-RISK-AI-001 (Risk Register entry RI-002)                                                                                     |

---

### SE-002 - PatientFlow Chatbot

| Field                    | Detail                                                                                                                       |
| ------------------------ | ---------------------------------------------------------------------------------------------------------------------------- |
| **System name**          | PatientFlow Chatbot                                                                                                          |
| **Vendor**               | PatientFlow Health Tech (fictional)                                                                                          |
| **System ID**            | SE-002                                                                                                                       |
| **Authorization status** | Under Evaluation - not authorized for patient-facing use                                                                     |
| **Evaluation started**   | February 2026                                                                                                                |
| **Risk tier**            | Medium                                                                                                                       |
| **Use case**             | LLM-powered patient intake assistant: appointment scheduling, insurance pre-verification, symptom triage routing             |
| **Users (proposed)**     | Patient-facing (external) + administrative staff                                                                             |
| **PHI processed**        | Yes - demographics, insurance info, self-reported symptoms; minimum necessary                                                |
| **BAA status**           | Draft received, under Legal review                                                                                           |
| **HITL requirement**     | Yes - any clinical routing decision (e.g., directing patient to ED) must trigger staff escalation                            |
| **Evaluation criteria**  | BAA execution, security assessment, prompt injection testing (MC-RT-AI-001), patient privacy impact assessment, AGC approval |
| **Current status**       | BAA under Legal review. Prompt injection testing scheduled for Q2 2026.                                                      |
| **Blocking issues**      | BAA not executed, prompt injection test not yet completed                                                                    |
| **Estimated approval**   | Q3 2026 pending Legal and testing completion                                                                                 |
| **Document ref**         | MC-RISK-AI-001 (Risk Register entry RI-003)                                                                                  |

---

## Unauthorized / Shadow AI

### SA-001 - Public LLM Use (ChatGPT, Claude, Gemini)

| Field                              | Detail                                                                                                                                                                         |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **System name**                    | Public LLMs (ChatGPT, Claude.ai, Google Gemini, Microsoft Copilot - consumer tiers)                                                                                            |
| **Vendor**                         | Multiple (OpenAI, Anthropic, Google, Microsoft)                                                                                                                                |
| **System ID**                      | SA-001                                                                                                                                                                         |
| **Authorization status**           | UNAUTHORIZED - active risk, highest priority                                                                                                                                   |
| **Risk tier**                      | Critical                                                                                                                                                                       |
| **Discovery method**               | Staff self-disclosure (Shadow AI Discovery initiative, Q1 2026); IT network traffic analysis                                                                                   |
| **Use cases observed**             | Clinical note summarization, patient communication drafting, medical coding assistance, and administrative document drafting                                                   |
| **PHI exposure**                   | Confirmed - staff have pasted patient names, diagnoses, treatment notes, and billing information into consumer LLM interfaces                                                  |
| **BAA status**                     | None of the consumer LLM tiers explicitly prohibit HIPAA use in their terms of service                                                                                         |
| **Affected departments**           | Nursing (primary), Billing (secondary), Administrative (lower volume)                                                                                                          |
| **Estimated users**                | 15-25 staff based on discovery interviews (17% of staff consistent with Wolters Kluwer 2025 benchmark)                                                                         |
| **Data handling by vendor**        | Consumer LLM tiers may use inputs to improve models per vendor ToS, no data processing agreements in place                                                                     |
| **HIPAA exposure**                 | High - PHI in unauthorized external system with no BAA constitutes a potential HIPAA breach under 45 CFR 164.402                                                               |
| **Current mitigation**             | AI AUP issued (MC-POL-AI-001), Shadow AI Reporting Channel active, staff training scheduled Q2 2026                                                                            |
| **Recommended action**             | (1) Deploy authorized enterprise LLM with BAA as an alternative, (2) Complete staff training, (3) Assess whether historical PHI exposure requires breach notification analysis |
| **Breach notification assessment** | Pending - Privacy Officer to assess whether discovered PHI disclosures meet HIPAA breach notification threshold                                                                |
| **Document ref**                   | Shadow AI Discovery Report (MC-DISC-AI-001), MC-RISK-AI-001 (Risk Register entry RI-004)                                                                                       |

**Source (17% benchmark):** [Wolters Kluwer Shadow AI in Healthcare survey (2025)](https://www.wolterskluwer.com/en/news/wolters-kluwer-survey-finds-broad-presence-of-unsanctioned-ai-tools-in-hospitals-and-health-systems)

---

## Inventory Change Log

| Date       | Change                                             | Author         |
| ---------- | -------------------------------------------------- | -------------- |
| April 2026 | Initial inventory created, four systems documented | D'Arcy Bracken |

---

## Next Steps

- [ ] Complete DiagnoAI vendor assessment (MC-VEN-AI-001) - due Q2 2026
- [ ] Execute PatientFlow BAA - pending Legal (due Q2 2026)
- [ ] Privacy Officer breach notification assessment for SA-001 historical PHI disclosures
- [ ] Deploy authorized enterprise LLM alternative to address SA-001 Shadow AI demand
- [ ] Semi-annual full inventory review - due October 2026

---

*MedCore Health Systems - Internal Use Only*
*MC-INV-AI-001 v1.0 - AI Use Case Inventory*

[Back to Project Overview](AI%20Change%20Mgmt%20RMF%20-%20(Overview).md) | [Shadow AI Discovery Report](Shadow%20AI%20Discovery%20Report.md)
