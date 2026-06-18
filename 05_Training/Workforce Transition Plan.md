---
document-id: MC-WFT-AI-001
framework: NIST AI RMF 1.0 - MANAGE 4.2; GOVERN 4.2
regulatory: HIPAA 45 CFR 164.308(a)(5)
version: 1
status: draft
---

# MC-WFT-AI-001 - Workforce Transition Plan

**MedCore Health Systems**
*AI Change Management - Workforce Readiness - Version 1.0*

---

## Purpose

AI adoption at MedCore changes how staff work. This plan addresses the human side of that change: how staff are prepared, supported, and repositioned as AI tools enter their workflows. It is explicitly not a downsizing plan. MedCore's AI deployment is designed to reduce administrative burden and support clinical decision-making, not to eliminate positions.

The plan is built on a **Human-as-a-Sensor** model: staff who understand AI's limitations are the most effective line of defense against AI errors, PHI exposure, and automation bias. A workforce that trusts its own judgment and knows when to override the AI is a security control.

---

## Transition Principles

1. **Transparency first.** Staff are told what AI will and will not do before it is deployed. No surprises.
2. **HITL is non-negotiable.** No authorized AI system at MedCore operates autonomously on clinical or financial decisions. Human review is always the final step.
3. **Skills shift, not elimination.** The work changes; the people doing it do not. Administrative time saved by AI is redirected to higher-value patient interaction and quality review.
4. **Non-punitive disclosure.** Staff who come forward about Shadow AI use or AI-related concerns are treated as allies, not violators.
5. **Feedback loops.** Staff observations of AI errors, unexpected outputs, and anomalous behavior are formal input into the AI governance program. The Human-as-a-Sensor model only works if staff believe their reports matter.

---

## Stakeholder Impact by Role

### Clinical Staff (Physicians, Nurses, Allied Health)

**AI systems affecting this group:** DiagnoAI (physicians), PatientFlow (intake and routing), potential note summarization tools (future)

| Change                                             | What It Means                                                                           | Support Provided                                                 |
| -------------------------------------------------- | --------------------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| DiagnoAI flags imaging findings for review         | Physician reviews AI flag plus their own assessment, documents when they agree/disagree | Training on reading confidence scores, automation bias awareness |
| PatientFlow handles initial patient triage routing | Clinical staff review routing decisions for urgent/complex cases                        | Escalation trigger training; clear override protocol             |
| AI note summarization (future)                     | Reduces documentation burden; physician approves before committing to chart             | PHI handling training, HITL workflow design                      |

**Key message for clinical staff:** AI is a second opinion, not a replacement for clinical judgment. Your expertise is the control.

### Billing and Coding Staff

**AI systems affecting this group:** AutoCode Billing Assistant

| Change                             | What It Means                                                                        | Support Provided                                        |
| ---------------------------------- | ------------------------------------------------------------------------------------ | ------------------------------------------------------- |
| AutoCode suggests ICD-10/CPT codes | Staff reviews all suggestions before submission, catches errors that AutoCode misses | Training on AutoCode limitations, verification workflow |
| Audit trail documentation          | Staff documents review decisions in billing system                                   | Process documentation, system configuration             |

**Key message for billing staff:** AutoCode reduces lookup time but does not reduce accountability. Every submitted code is your responsibility.

### Administrative Staff

**AI systems affecting this group:** PatientFlow (scheduling), potential document drafting tools (future)

| Change                                            | What It Means                                                                                     | Support Provided                                           |
| ------------------------------------------------- | ------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| PatientFlow handles appointment scheduling intake | Staff focuses on exception handling, complex cases, patient questions the chatbot escalates       | Escalation training, clear handoff protocols               |
| AI-assisted document drafting (future)            | Administrative documents can be drafted faster, and staff reviews can be conducted before sending | PHI handling, HITL requirements for patient communications |

**Key message for administrative staff:** Time saved on routine scheduling goes back to you for higher-value work. Shadow AI is no longer necessary authorized tools will be available.

---

## The Human-as-a-Sensor Model

Staff observations are MedCore's most valuable AI monitoring signal. The output anomaly monitor catches technical signals, staff catch behavioral anomalies that no automated system would recognize.

**What staff are asked to notice and report:**

- AI responses that seem "off" confident claims about things the system shouldn't know
- Responses that are far longer or shorter than expected
- Responses that reference other patients or cases not in the current interaction
- Clinical recommendations that don't match the presentation
- Any response that starts with unexpected formatting or structure (potential injection artifact)

**What happens when they report:**
- IT Security triages within 1 business day
- PHI-adjacent reports escalate to Privacy Officer same day
- Staff receive acknowledgment within 24 hours
- Aggregate findings are reported to AGC quarterly (anonymized)
- Staff who identify a genuine AI security issue are recognized at the department level

**Why this matters for compliance:** The January 2025 HHS HIPAA Security Rule NPRM explicitly increases expectations for AI monitoring. A workforce trained to observe and report is a compliance asset, not a compliance burden.

---

## Communication Plan

### Pre-Deployment (Before Any AI System Goes Live)

| Audience | Message | Channel | Owner |
|----------|---------|---------|-------|
| All staff | AI governance program launched; AI AUP effective immediately | All-staff email from CISO | CISO |
| All staff | Non-punitive disclosure: how to report Shadow AI | Department meetings | HR + Department Managers |
| Clinical staff | DiagnoAI and PatientFlow evaluation underway; not yet authorized | Department-level briefing | CMO |
| Billing staff | AutoCode now conditionally authorized; training required | Billing manager briefing | Billing Manager + CISO |

### At Deployment of Each System

| Step              | Activity                                                                       | Owner                     |
| ----------------- | ------------------------------------------------------------------------------ | ------------------------- |
| 30 days before    | Preview session: what the system does, what it doesn't do; how HITL works      | Department Manager + IT   |
| 2 weeks before    | Role-specific training module available in LMS                                 | HR                        |
| 1 week before     | Q&A session with the department, concerns documented                           | Department Manager        |
| Day of deployment | IT support available; escalation contacts distributed                          | IT Security               |
| 30 days after     | First feedback session: what is working, what isn't                            | Department Manager + CISO |
| 90 days after     | First post-deployment review: anomaly reports, HITL compliance, staff feedback | CISO + AGC                |

---

## Skills Development

AI deployment creates demand for new competencies. MedCore will support development of:

| Competency | Audience | Development Path |
|------------|----------|-----------------|
| AI output verification | All clinical and billing staff | Core + role-specific training modules |
| Prompt hygiene (authorized enterprise LLM users) | Admin staff with approved LLM access | Module added to core training when enterprise LLM deployed |
| AI anomaly recognition | All staff | Core training + manager reinforcement |
| AI governance (NIST AI RMF awareness) | CISO, IT Security, Privacy Officer | External training / conference (annual budget) |
| AI vendor assessment | IT Security lead | MC-VEN-AI-001 working knowledge; vendor security training |

---

## Feedback and Continuous Improvement

The Workforce Transition Plan is a living document. It is updated based on:

- Post-deployment feedback sessions (30- and 90-day)
- AI Anomaly Report patterns (are staff reporting? are reports actionable?)
- HITL compliance audit results
- Staff exit interviews where AI experience is relevant
- AGC quarterly review findings

**Plan review cadence:** Semi-annual, or following any AI security incident affecting staff.

---

## Version History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | April 2026 | D'Arcy Bracken | Initial plan |

---

*MedCore Health Systems - Internal Use Only*
*MC-WFT-AI-001 v1.0 - Workforce Transition Plan*

[Back to Project Overview](AI%20Change%20Mgmt%20RMF%20-%20(Overview).md) | [AI Literacy Program](AI%20Literacy%20Program.md) | [Governance Charter](AI%20Governance%20Charter.md)
