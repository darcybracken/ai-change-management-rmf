---
document-id: MC-DISC-AI-001
framework: NIST AI RMF 1.0 - MAP Function
regulatory: HIPAA, HITECH
version: 1
status: draft
assessment_period: Q1 2026 (January - March)
conducted_by: IT Security Team
---

# MC-DISC-AI-001 - Shadow AI Discovery Report

**MedCore Health Systems**
*Confidential Internal Assessment - Version 1.0*

**Confidentiality**

This report contains findings about unauthorized AI use and potential PHI exposure. Distribution is restricted to: CISO, Privacy Officer, CMO, and AI Governance Committee members. Do not distribute to the general staff.

---

## Executive Summary

During Q1 2026, MedCore IT Security conducted a Shadow AI discovery assessment combining network traffic analysis, staff interviews, and voluntary self-disclosure. The assessment found that **unauthorized use of AI tools is active and widespread across clinical and administrative departments, with confirmed PHI exposure in at least 3 instances.

**Key findings:**

- An estimated 15-25 staff members (~11-17% of the workforce) have used public LLMs for work purposes
- PHI has been entered into unauthorized AI systems by at least 8 staff members across nursing and billing
- Primary driver is workflow speed: staff lack approved AI alternatives for note summarization and documentation
- No staff were using AI with malicious intent, all known uses were workflow-motivated
- The organizational risk is not employee misconduct, it is the absence of governed AI alternatives

**Recommended immediate actions:**
1. Privacy Officer breach notification assessment for confirmed PHI disclosures
2. Expedite enterprise LLM procurement with BAA
3. Complete staff AI literacy training (Q2 2026)
4. Communicate non-punitive self-disclosure policy broadly

---

## Assessment Methodology

### Discovery Channels

| Method                            | Coverage                                        | Findings                                                                                          |
| --------------------------------- | ----------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Network traffic analysis          | All MedCore networks (3 clinics + admin office) | Outbound traffic to openai.com, claude.ai, gemini.google.com identified from 12 unique device IPs |
| IT Help Desk query analysis       | Q4 2025 - Q1 2026 tickets                       | 4 tickets referencing AI tools, 2 asked about "ChatGPT for notes"                                 |
| Voluntary staff interviews        | 22 staff across 4 departments                   | 8 staff disclosed personal AI use, 14 reported awareness of colleagues                            |
| Anonymous self-disclosure channel | Organization-wide                               | 3 self-disclosures received, all billing/admin use                                                |
| Manager interviews                | 6 department managers                           | 4 managers aware of team AI use; 2 unaware                                                        |

### Scope and Limitations

This assessment covers MedCore's three clinic locations and administrative office. It does not cover:
- Staff personal devices used outside MedCore networks (scope limitation, likely underestimates true prevalence)
- Vendor systems that may incorporate AI without MedCore's knowledge (vendor assessment ongoing per MC-VEN-AI-001)
- Historical use prior to Q4 2025 (not assessed)

---

## Detailed Findings

### Finding 1: Active PHI Exposure via Consumer LLMs (Critical)

**What was found:** At least 8 staff members confirmed entering PHI into consumer LLM interfaces, primarily ChatGPT (OpenAI consumer tier) and Claude.ai (Anthropic consumer tier). Disclosed use cases include:

- Nursing staff copying and pasting clinical notes into ChatGPT for summarization before shift handoffs
- A billing specialist using ChatGPT to draft appeal letters, including patient name, diagnosis, and insurance ID
- An administrative coordinator using Claude.ai to draft patient communications including appointment details and referring physician names

**PHI categories confirmed exposed:**
- Patient names: Yes
- Dates of service: Yes
- Diagnoses and ICD-10 codes: Yes
- Insurance information: Yes
- Clinical notes: Yes (partial -- nursing summaries)
- Imaging data: No (not confirmed)
- SSN / financial: Not confirmed

**HIPAA analysis:** Consumer LLM tiers (ChatGPT Free/Plus, Claude.ai consumer) are not HIPAA-compliant. OpenAI and Anthropic consumer terms of service do not include Business Associate Agreements and explicitly state that inputs may be used to improve models. Entry of PHI into these systems constitutes disclosure to a third party without authorization meeting the preliminary definition of a HIPAA breach under 45 CFR 164.402.

**Immediate action required:** Privacy Officer breach notification assessment to determine whether discovered disclosures meet the threshold for HHS OCR reporting under the HIPAA Breach Notification Rule (45 CFR 164.400-414). Assessment must consider: (1) nature of PHI disclosed, (2) likelihood PHI was accessed or used impermissibly, (3) extent to which risk has been mitigated.

---

### Finding 2: Workflow Gap is the Root Cause (High)

**What was found:** Staff using Shadow AI are not doing so for malicious reasons. In every interview, the primary motivation was speed: note summarization, documentation drafting, and coding assistance that would take significantly longer to complete manually. No approved alternative exists for these use cases.

**Staff quotes (anonymized):**
- "I just needed the summary done before the next patient. I didn't think about where the data was going."
- "If IT gave us something that did this, I'd use that instead."
- "I know I shouldn't, but no one ever told us we couldn't."

**Implication:** Blocking access to consumer AI without providing an approved alternative will not eliminate Shadow AI use, it will push it to personal devices off the MedCore network, making it invisible to monitoring. The governance solution is an approved AI alternative, not only a prohibition.

**Recommended action:** Prioritize the expedited evaluation and procurement of an enterprise-level language model (LLM) with a signed Business Associate Agreement (BAA). Options include Azure OpenAI Service, AWS Bedrock, or Google Vertex AI, all of which offer HIPAA-compliant BAAs. This action addresses the workflow requirement while ensuring the protection of patient health information (PHI) within the defined governance boundaries.

---

### Finding 3: Manager Awareness Gap (Medium)

**What was found:** Four of six interviewed managers were aware that team members were using AI tools, but did not consider it their responsibility to report or intervene. Two managers were entirely unaware. No manager had received guidance on what to do when they observed AI tool use.

**Implication:** The AI AUP (MC-POL-AI-001) places first-line escalation responsibility on department managers. Without explicit training on this responsibility, managers cannot fulfill it.

**Recommended action:** Manager-specific AI governance training covering: escalation obligations, how to report Shadow AI observations, and the non-punitive self-disclosure policy for staff they supervise.

---

### Finding 4: Positive Response to Non-Punitive Channel (Low-Medium)

**What was found:** The anonymous self-disclosure channel received 3 reports within two weeks of launch. All three were good-faith disclosures from staff who had not previously been aware that their AI use was a problem. All three expressed willingness to stop and use an approved alternative if available.

**Implication:** A non-punitive approach is working. Staff are willing to disclose when they trust that they will not face punishment for honest reports. The Wolters Kluwer 2025 survey found that 45% of staff using unauthorized AI did so for faster workflow, not malicious intent, which is consistent with what these disclosures show: trust and approved alternatives, not enforcement, are the effective interventions.

**Source:** [Wolters Kluwer Shadow AI in Healthcare survey (2025)](https://www.wolterskluwer.com/en/news/wolters-kluwer-survey-finds-broad-presence-of-unsanctioned-ai-tools-in-hospitals-and-health-systems)

---

## Risk Summary

| Finding                        | Risk Level | HIPAA Implication                                   | Status     |
| ------------------------------ | ---------- | --------------------------------------------------- | ---------- |
| PHI in consumer LLMs           | Critical   | Potential breach - notification assessment required | Active     |
| No approved AI alternative     | High       | Structural driver of ongoing Shadow AI risk         | Mitigating |
| Manager awareness gap          | Medium     | Escalation chain broken                             | Mitigating |
| Non-punitive channel effective | Positive   | Supports voluntary disclosure and trust             | Ongoing    |

---

## Recommended Actions and Owners

| Action | Owner | Priority | Target Date |
|--------|-------|----------|------------|
| Privacy Officer breach notification assessment | Privacy Officer | Critical | Within 30 days |
| Expedite enterprise LLM procurement with BAA | CISO + CFO | High | Q2 2026 |
| Deliver staff AI literacy training | HR + CISO | High | Q2 2026 |
| Manager AI governance training | HR + CISO | Medium | Q2 2026 |
| Communicate non-punitive self-disclosure policy | CISO + HR | Medium | Immediate |
| Re-run Shadow AI discovery assessment | IT Security | Low | Q4 2026 (post-training) |

---

## Version History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | April 2026 | D'Arcy Bracken | Initial assessment |

---

*MedCore Health Systems - Confidential Internal Use Only*
*MC-DISC-AI-001 v1.0 - Shadow AI Discovery Report*

[Back to Project Overview](AI%20Change%20Mgmt%20RMF%20-%20(Overview).md) | [AI Use Case Inventory](AI%20Use%20Case%20Inventory.md)
