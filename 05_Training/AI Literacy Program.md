---
document-id: MC-TRAIN-AI-001
framework: NIST AI RMF 1.0 - MANAGE 4.2
regulatory: HIPAA 45 CFR 164.308(a)(5)
version: 1
status: draft
---

# MC-TRAIN-AI-001 - AI Literacy Program

**MedCore Health Systems**
*Workforce Training Program Outline - Version 1.0*

---

## Program Overview

| Field           | Detail                                                                 |                                      |
| --------------- | ---------------------------------------------------------------------- | ------------------------------------ |
| **Audience**    | All MedCore staff (all roles, all locations)                           |                                      |
| **Delivery**    | Annual mandatory role-specific modules for clinical AI users           |                                      |
| **Format**      | Online self-paced (core module) + department-led discussion (optional) |                                      |
| **Duration**    | Core module: 30 minutes                                                | Role-specific: 20 additional minutes |
| **Frequency**   | Annual triggered re-training following any AI security incident        |                                      |
| **Tracking**    | HR LMS, completion reported to CISO quarterly                          |                                      |
| **NIST AI RMF** | MANAGE 4.2 - AI risks and limitations communicated to users            |                                      |
| **HIPAA**       | 45 CFR 164.308(a)(5) - Security Awareness and Training                 |                                      |

---

## Module 1 - Core: AI at MedCore (All Staff, 30 min)

### Learning Objectives

By the end of this module, staff will be able to:

1. Explain what AI tools are and why MedCore governs their use
2. Identify which AI tools are authorized for use at MedCore
3. Describe what constitutes PHI and why it must never enter unauthorized AI systems
4. Know how to report Shadow AI use or AI-related concerns
5. Find the AI Acceptable Use Policy and understand its key rules

### Content Outline

**Unit 1.1 - What is AI and what can it do? (5 min)**
- Plain-language explanation of LLMs, decision-support AI, and diagnostic AI
- Examples relevant to healthcare: note summarization, coding assistance, diagnostic imaging
- Key concept: AI generates outputs based on training data - it does not "know" things the way a human expert does

**Unit 1.2 - Why MedCore has AI governance (5 min)**
- Shadow AI: what it is and why it matters
- Real example: staff using ChatGPT with patient notes - what actually happens to that data
- Statistic: 17% of healthcare workers have used unauthorized AI tools (Wolters Kluwer 2025)
- The 2025 Covenant Health breach (478,188 patients): how a third-party compromise becomes the covered entity's liability
- Key concept: "I didn't know" is not a HIPAA defense - intent does not determine breach status

**Sources:** [Wolters Kluwer Shadow AI in Healthcare survey (2025)](https://www.wolterskluwer.com/en/news/wolters-kluwer-survey-finds-broad-presence-of-unsanctioned-ai-tools-in-hospitals-and-health-systems) · [HIPAA Journal, Covenant Health cyberattack (2025)](https://www.hipaajournal.com/covenant-health-cyberattack/)

**Unit 1.3 - PHI and AI: the rules (10 min)**
- What is PHI: definition and examples specific to MedCore workflows
- Data classification quick reference (from MC-POL-AI-001 Section 7)
- The two rules: (1) PHI never goes into an unauthorized AI system, (2) when in doubt, don't
- What "authorized AI" means: BAA, IT review, CISO approval, on the authorized list
- What happens to data in consumer LLMs (model training, third-party sharing)

**Unit 1.4 - Hallucinations, automation bias, and HITL (5 min)**
- What AI hallucinations are: confident but wrong outputs
- Automation bias: why humans tend to trust AI more than they should over time
- HITL: What it means to review AI output before acting on it
- Clinical context: AI suggests; clinician decides

**Unit 1.5 - How to report and what happens next (5 min)**
- AI Anomaly Reporting Channel: email, portal, verbal - all options
- Non-punitive policy: self-disclosure before an incident is treated differently
- What IT Security does with a report: triage within 1 business day
- What happens if PHI exposure is confirmed: Privacy Officer assessment, not immediate punishment

### Knowledge Check (5 questions)

1. Which of the following is PHI? [multiple choice with examples]
2. A colleague asks you to help summarize a patient's chart using ChatGPT. What do you do?
3. An AI tool gives you a confident-sounding clinical recommendation. What is the right next step?
4. Where do you report an AI security concern at MedCore?
5. Which of these AI tools is currently authorized for use at MedCore? [list with one correct answer]

---

## Module 2 - Clinical AI Users: Role-Specific Training (20 min)

**Audience:** Staff who use DiagnoAI, PatientFlow, or AutoCode as part of their role.

### Learning Objectives

1. Understand the specific capabilities and limitations of the AI system in its role
2. Apply HITL correctly: when and how to review AI output before acting
3. Recognize signs that an AI system may be malfunctioning or producing anomalous output
4. Know how to escalate a clinical AI concern

### Content Outline

**Unit 2.1 - Your AI system: what it does and what it doesn't do (8 min)**

*AutoCode track:* ICD-10/CPT code suggestions - accuracy limitations; why verification is required; how to spot outdated code suggestions, False Claims Act risk if wrong codes submitted without review.

*DiagnoAI track (when authorized):* Imaging analysis as second-read support false negative rates in AI diagnostic tools, why physician sign-off is mandatory on all outputs, how to read DiagnoAI confidence scores, and what to do when you disagree with an AI finding.

*PatientFlow track (when authorized):* Chatbot triage limitations, symptoms the chatbot may under-triage, escalation triggers (chest pain, stroke symptoms, any urgent presentation), and how to override a chatbot routing recommendation.

**Unit 2.2 - HITL in practice (7 min)**
- Scenario walkthroughs: what HITL looks like for each system
- Common HITL failure: accepting AI output without checking because it "looks right"
- Automation bias in clinical settings: documented examples from published research
- Documentation: if you override an AI recommendation, document why

**Unit 2.3 - Escalation (5 min)**
- Signs that an AI system is producing anomalous output: unexpected responses, out-of-scope content, unusually confident claims about data it shouldn't have access to
- Immediate escalation: CMO + IT Security; do not continue using the system; preserve the output
- AI Anomaly Reporting Channel contact information

---

## Module 3 - Manager Track: Escalation Responsibilities (15 min)

**Audience:** All department managers.

### Learning Objectives

1. Know the manager's role in the AI governance RACI
2. Be able to identify Shadow AI use in their team and escalate appropriately
3. Deliver the non-punitive disclosure message to staff

### Content Outline

**Unit 3.1 - Your role in AI governance (5 min)**
- From the RACI Matrix: managers are the first-line escalation point for AI concerns
- What that means practically: if you observe or learn about Shadow AI use, you report it
- Non-punitive culture: how you discuss AI concerns with staff affects whether they disclose
- The manager who says, "I'm not going to get anyone in trouble," creates disclosure safety

**Unit 3.2 - How to have the Shadow AI conversation (5 min)**
- Script: How to ask a staff member about their AI tool use without creating defensiveness
- What to do with the information: report to IT Security within 24 hours
- What you do NOT do: investigate independently, access staff devices, or determine breach status yourself

**Unit 3.3 - Escalation and follow-through (5 min)**
- IT Security escalation: email ai-safety@medcorehealthsystems.org with date, staff role (not name if initial report), and tool used
- Privacy Officer escalation: if PHI involvement is confirmed or suspected
- Your follow-up: confirm staff completes AI literacy training; document the conversation

---

## Training Completion and Compliance

| Metric | Target | Tracking |
|--------|--------|---------|
| Core module completion | 100% of staff within 60 days of hire | HR LMS |
| Annual re-completion | 100% by December 31 each year | HR LMS |
| Clinical AI module (role-specific users) | 100% before first authorized system use | HR LMS |
| Manager track | 100% of managers within 30 days of program launch | HR LMS |
| Post-incident re-training | Assigned staff within 2 weeks | IT Security + HR |

Non-completion is reported to the CISO and relevant department manager. Persistent non-completion is escalated to HR as a policy compliance matter.

---

## Version History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | April 2026 | D'Arcy Bracken | Initial program outline |

---

*MedCore Health Systems - Internal Use Only*
*MC-TRAIN-AI-001 v1.0 - AI Literacy Program*

[Back to Project Overview](AI%20Change%20Mgmt%20RMF%20-%20(Overview).md) | [Workforce Transition Plan](Workforce%20Transition%20Plan.md) | [AI AUP](AI%20Acceptable%20Use%20Policy.md)
