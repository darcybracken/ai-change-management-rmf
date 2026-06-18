---
document-id: MC-XWALK-AI-001
framework: NIST AI RMF 1.0 x HIPAA Privacy Rule x HIPAA Security Rule x HITECH
regulatory: HIPAA, HITECH
version: 1
status: draft
---
# MC-XWALK-AI-001 - NIST AI RMF x HIPAA Crosswalk

**MedCore Health Systems**
*Internal GRC Reference Document - Version 1.0*


**Purpose and audience**

This crosswalk maps the NIST AI Risk Management Framework 1.0 subcategories to applicable HIPAA Privacy Rule, HIPAA Security Rule, and HITECH provisions. It is the primary reference for MedCore's AI compliance analysis and is used by the CISO and Privacy Officer to demonstrate that AI governance activities satisfy existing HIPAA obligations. Audience: CISO, Privacy Officer, Legal Counsel, AGC members.


**Regulatory context**

HIPAA does not contain AI-specific regulations. However, OCR has confirmed that existing HIPAA Privacy Rule and Security Rule obligations apply fully to AI systems that process, store, or transmit PHI. The January 2025 HHS proposed HIPAA Security Rule update (NPRM) explicitly requires AI tools to be included in covered entities' risk analyses. This crosswalk treats existing HIPAA requirements as the binding obligations and maps AI RMF actions to them.

---

## How to Read This Crosswalk

| Column                 | Meaning                                           |
| ---------------------- | ------------------------------------------------- |
| AI RMF Function        | GOVERN / MAP / MEASURE / MANAGE                   |
| AI RMF Subcategory     | Specific AI RMF subcategory code and description  |
| HIPAA / HITECH Mapping | Applicable regulatory citation                    |
| MedCore Implementation | How MedCore satisfies this at present or plans to |
| Gap                    | Y = gap exists, N = control in place, P = planned |
| Document Reference     | MedCore document that addresses this requirement  |

---

## GOVERN Function

The GOVERN function establishes accountability structures, policies, and organizational practices for responsible AI.

| AI RMF Subcategory | Description                                                            | HIPAA / HITECH Mapping                                  | MedCore Implementation                                                                                                                   | Gap | Document Ref                 |
| ------------------ | ---------------------------------------------------------------------- | ------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | --- | ---------------------------- |
| GOVERN 1.1         | Policies and processes exist for AI risk governance and oversight      | 45 CFR 164.308(a)(1)(i) - Risk Management Policy        | AI Governance Charter (MC-GOV-AI-002) and AI AUP (MC-POL-AI-001) established Q1 2026                                                     | N   | MC-GOV-AI-002, MC-POL-AI-001 |
| GOVERN 1.2         | Accountability for AI risk is assigned to specific roles               | 45 CFR 164.308(a)(2) - Assigned Security Responsibility | CISO designated AI risk owner, Privacy Officer designated for PHI compliance, RACI matrix documents all role assignments                 | N   | MC-GOV-AI-001                |
| GOVERN 1.4         | AI supply chain risks are managed                                      | 45 CFR 164.308(b) - Business Associate Contracts        | BAA required for all AI vendors processing PHI, AutoCode BAA executed, DiagnoAI, and PatientFlow BAAs pending                            | P   | MC-VEN-AI-001                |
| GOVERN 1.6         | Policies address the use of AI by third parties                        | 45 CFR 164.308(b)(1) - Business Associate Contracts     | Vendor contracts require BAA, security assessment (MC-VEN-AI-001) required before authorization                                          | P   | MC-VEN-AI-001                |
| GOVERN 2.1         | Legal and regulatory requirements for AI are understood                | 45 CFR 164.306(a) - General Requirements, HITECH 13401  | HIPAA applicability to AI confirmed, HHS 2025 NPRM reviewed, OWASP LLM Top 10 incorporated into red team scope                           | N   | MC-XWALK-AI-001              |
| GOVERN 2.2         | Policies require documentation of AI system context, purpose, and data | 45 CFR 164.308(a)(1)(ii)(A) - Risk Analysis             | AI Use Case Inventory (MC-INV-AI-001) documents all systems, data flows, PHI exposure, and risk tier                                     | N   | MC-INV-AI-001                |
| GOVERN 4.1         | AI risk tolerance is defined and communicated                          | 45 CFR 164.308(a)(1)(ii)(B) - Risk Management           | Risk tier classification and residual risk thresholds defined in AI Risk Register (MC-RISK-AI-001), AGC escalation threshold at score 12 | N   | MC-RISK-AI-001               |
| GOVERN 6.1         | Policies address AI system anomaly and incident reporting              | 45 CFR 164.308(a)(6) - Security Incident Procedures     | AI Anomaly Reporting Channel active, AI IR Addendum (MC-IRP-AI-001) extends existing IRP                                                 | P   | MC-IRP-AI-001                |

---

## MAP Function

The MAP function identifies AI context, intended uses, risk categories, and organizational conditions.

| AI RMF Subcategory | Description                                                          | HIPAA / HITECH Mapping                                                    | MedCore Implementation                                                                                                                               | Gap | Document Ref                  |
| ------------------ | -------------------------------------------------------------------- | ------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | --- | ----------------------------- |
| MAP 1.1            | Context of AI system use is documented (purpose, users, environment) | 45 CFR 164.308(a)(1)(ii)(A) - Risk Analysis                               | AI Use Case Inventory documents system purpose, user groups, and deployment context for each AI system                                               | N   | MC-INV-AI-001                 |
| MAP 1.5            | Organizational risk tolerance for AI is documented                   | 45 CFR 164.308(a)(1)(ii)(B) - Risk Management                             | Risk tier definitions and residual risk appetite documented in Risk Register preamble                                                                | N   | MC-RISK-AI-001                |
| MAP 2.2            | Scientific and domain knowledge about AI risks is applied            | 45 CFR 164.308(a)(1)(ii)(A) - Risk Analysis                               | OWASP LLM Top 10, NIST AI RMF Playbook, and CISA AI security guidelines used as risk taxonomy sources                                                | N   | MC-RT-AI-001                  |
| MAP 2.3            | AI data governance is defined: data sources, quality, and privacy    | 45 CFR 164.514 - De-identification; 45 CFR 164.502(b) - Minimum Necessary | Data classification table in AI AUP, minimum necessary standard applied to all AI interactions; de-identified pilot required for DiagnoAI evaluation | N   | MC-POL-AI-001                 |
| MAP 3.5            | Risks from third-party AI components are identified                  | 45 CFR 164.308(b) - Business Associate Contracts                          | Shadow AI Discovery Report identifies unauthorized third-party AI use, vendor assessment process addresses authorized third-party risk               | N   | MC-DISC-AI-001, MC-VEN-AI-001 |
| MAP 5.1            | AI system limitations and failure modes are documented               | 45 CFR 164.308(a)(1)(ii)(A) - Risk Analysis                               | AI AUP Section 6.4 (hallucinations), Risk Register entries for model drift (RI-006), automation bias (RI-008), unsafe routing (RI-009)               | P   | MC-RISK-AI-001, MC-POL-AI-001 |
| MAP 5.2            | Impacts of AI failure on individuals are assessed                    | 45 CFR 164.306(a)(1) -Confidentiality, Integrity, Availability            | Risk Register impact ratings assess patient safety, PHI disclosure, and operational impact per system                                                | N   | MC-RISK-AI-001                |

---

## MEASURE Function

The MEASURE function analyzes and assesses AI risks using quantitative and qualitative methods.

| AI RMF Subcategory | Description                                                        | HIPAA / HITECH Mapping                                                                               | MedCore Implementation                                                                                                                                                                                                                                                                                          | Gap | Document Ref                  |
| ------------------ | ------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --- | ----------------------------- |
| MEASURE 1.1        | Methods exist to measure AI risks                                  | 45 CFR 164.308(a)(1)(ii)(A) - Risk Analysis                                                          | 5x5 likelihood/impact risk scoring used in AI Risk Register, 10 risks documented with inherent and residual scores                                                                                                                                                                                              | N   | MC-RISK-AI-001                |
| MEASURE 2.2        | AI system risks are evaluated in context of deployment             | 45 CFR 164.308(a)(1)(ii)(A) - Risk Analysis                                                          | Each AI system assessed separately in Risk Register with deployment-specific threat scenarios                                                                                                                                                                                                                   | N   | MC-RISK-AI-001                |
| MEASURE 2.5        | AI system performance is evaluated against intended purpose        | 45 CFR 164.308(a)(1)(ii)(A) - Risk Analysis; 45 CFR 164.312(b) - Audit Controls                      | AutoCode: HITL provides ongoing performance feedback, DiagnoAI: clinical validation pilot required, PatientFlow: prompt injection testing required                                                                                                                                                              | P   | MC-RISK-AI-001                |
| MEASURE 2.6        | AI system safety risks are assessed, including adversarial testing | 45 CFR 164.308(a)(6) - Security Incident Procedures; 45 CFR 164.308(a)(1) - Risk Analysis            | Red Team Playbook (MC-RT-AI-001) covers prompt injection testing for PatientFlow and DiagnoAI before authorization. Accountability: CISO (per RACI Matrix). Privacy Officer is Consulted because red team findings that confirm PHI exposure trigger breach notification assessment under 45 CFR 164.308(a)(6). | P   | MC-RT-AI-001                  |
| MEASURE 2.7        | AI supply chain risks are evaluated                                | 45 CFR 164.308(b) - Business Associate Contracts                                                     | Vendor Assessment Checklist (MC-VEN-AI-001) evaluates supply chain risk for each AI vendor, BAA requirement is the minimum threshold                                                                                                                                                                            | P   | MC-VEN-AI-001                 |
| MEASURE 3.3        | AI system monitoring is in place post-deployment                   | 45 CFR 164.308(a)(1)(ii)(D) - Information System Activity Review, 45 CFR 164.312(b) - Audit Controls | AutoCode: quarterly IT log review, DiagnoAI/PatientFlow: monitoring plan to be defined at authorization, output anomaly monitoring defined in Red Team Playbook                                                                                                                                                 | P   | MC-RT-AI-001                  |
| MEASURE 4.1        | Risk measurement results inform decision-making                    | 45 CFR 164.308(a)(1)(ii)(B) - Risk Management                                                        | AGC reviews Risk Register quarterly, authorization decisions require a residual score below 8, RI-004 (Shadow AI) triggers a monthly review at a score 12                                                                                                                                                       | N   | MC-RISK-AI-001, MC-GOV-AI-002 |

---

## MANAGE Function

The MANAGE function prioritizes and treats AI risks through mitigation, monitoring, and incident response.

| AI RMF Subcategory | Description                                               | HIPAA / HITECH Mapping                                                                  | MedCore Implementation                                                                                                                                        | Gap | Document Ref                 |
| ------------------ | --------------------------------------------------------- | --------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | --- | ---------------------------- |
| MANAGE 1.3         | Risk treatment plans are implemented and tracked          | 45 CFR 164.308(a)(1)(ii)(B) - Risk Management                                           | Treatment column in Risk Register assigns owners and target dates, AGC tracks at quarterly meetings                                                           | N   | MC-RISK-AI-001               |
| MANAGE 2.2         | Controls are implemented to reduce AI risks               | 45 CFR 164.312 - Technical Safeguards                                                   | HITL requirements for all clinical AI, BAA requirements, Shadow AI reporting channel, staff training                                                          | P   | MC-POL-AI-001, MC-GOV-AI-002 |
| MANAGE 2.4         | AI system performance is monitored post-deployment        | 45 CFR 164.308(a)(1)(ii)(D) - Information System Activity Review                        | AutoCode monthly monitoring; expanded monitoring plan required for DiagnoAI and PatientFlow at authorization                                                  | P   | MC-INV-AI-001                |
| MANAGE 3.1         | AI system changes and updates are governed                | 45 CFR 164.308(a)(8) - Evaluation; 45 CFR 164.312(b) - Audit Controls                   | AI System Lifecycle in Governance Charter requires re-review at major model updates, and vendor contract to include a change notification requirement         | P   | MC-GOV-AI-002                |
| MANAGE 4.1         | AI incident response procedures exist                     | 45 CFR 164.308(a)(6) - Security Incident Procedures; HITECH 13402 - Breach Notification | AI IR Addendum (MC-IRP-AI-001) extends MedCore's existing IRP with AI-specific response procedures, HIPAA breach notification timeline (60 days) incorporated | P   | MC-IRP-AI-001                |
| MANAGE 4.2         | AI risks and limitations are communicated to stakeholders | 45 CFR 164.308(a)(5) - Security Awareness Training                                      | AI literacy training (annual, 30 min) covers HIPAA PHI risks, hallucinations, Shadow AI, and role-specific training for clinical AI users                     | P   | AI Literacy Program          |

---

## HIPAA to AI RMF Reverse Mapping

For compliance teams approaching this from the HIPAA side:

| HIPAA Requirement                | 45 CFR Citation      | AI RMF Function        | MedCore AI Implementation                                                                        |
| -------------------------------- | -------------------- | ---------------------- | ------------------------------------------------------------------------------------------------ |
| Risk Analysis                    | 164.308(a)(1)(ii)(A) | MEASURE 1.1, 2.2, 2.5  | AI Risk Register (MC-RISK-AI-001)                                                                |
| Risk Management                  | 164.308(a)(1)(ii)(B) | MANAGE 1.3, 2.2        | Risk Register treatment plans, AGC quarterly review                                              |
| Assigned Security Responsibility | 164.308(a)(2)        | GOVERN 1.2             | CISO as AI risk owner, RACI Matrix (MC-GOV-AI-001)                                               |
| Business Associate Contracts     | 164.308(b)           | GOVERN 1.4, 1.6        | BAA required for all AI vendors; vendor assessment (MC-VEN-AI-001)                               |
| Security Awareness Training      | 164.308(a)(5)        | MANAGE 4.2             | AI Literacy Program (annual), role-specific training                                             |
| Security Incident Procedures     | 164.308(a)(6)        | GOVERN 6.1, MANAGE 4.1 | AI Anomaly Reporting Channel, AI IR Addendum (MC-IRP-AI-001)                                     |
| Audit Controls                   | 164.312(b)           | MEASURE 3.3            | AI system logging, quarterly IT review; output anomaly monitoring                                |
| Minimum Necessary                | 164.502(b)           | MAP 2.3                | AI AUP Section 6.1, data classification table                                                    |
| Breach Notification              | 164.400-414          | MANAGE 4.1             | Privacy Officer breach notification assessment underway, AI IR Addendum includes 60-day timeline |
| De-identification                | 164.514              | MAP 2.3                | DiagnoAI pilot requires de-identified data, PHI not permitted until BAA executed                 |

---

## Compliance Gap Summary

| Gap Area | Risk | Priority | Owner | Status |
|----------|------|----------|-------|--------|
| DiagnoAI BAA not executed | RI-002, RI-003 | High | Legal + Privacy Officer | In progress |
| PatientFlow BAA not executed | RI-003 | High | Legal | In progress |
| Red team / prompt injection testing incomplete | RI-005 | High | IT Security | Planned Q2 2026 |
| Breach notification assessment (Shadow AI) | RI-004, RI-010 | Critical | Privacy Officer | Active -- 30-day deadline |
| Post-deployment monitoring plan for future systems | MEASURE 3.3 | Medium | IT Security | Planned at authorization |
| AI IR Addendum not yet finalized | MANAGE 4.1 | Medium | CISO | In progress |
| Staff AI training not yet delivered | MANAGE 4.2 | Medium | HR + CISO | Planned Q2 2026 |

---

## Version History

| Version | Date       | Author         | Changes                                              |
| ------- | ---------- | -------------- | ---------------------------------------------------- |
| 1.0     | April 2026 | D'Arcy Bracken | Initial crosswalk - all four AI RMF functions mapped |

---

*MedCore Health Systems - Internal Use Only*
*MC-XWALK-AI-001 v1.0 - NIST AI RMF x HIPAA Crosswalk*

[Back to Project Overview](AI%20Change%20Mgmt%20RMF%20-%20(Overview).md) | [AI Risk Register](AI%20Risk%20Register.md) | [Governance Charter](AI%20Governance%20Charter.md)
