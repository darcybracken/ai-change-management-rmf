---
document-id: MC-GOV-AI-002
framework: NIST AI RMF 1.0 - GOVERN Function
regulatory: HIPAA, HITECH
version: 1
status: draft
approved_by: Pending Executive Review
---

# MC-GOV-AI-002 - AI Governance Charter

**MedCore Health Systems**
*Internal Governance Document - Version 1.0*

---

## 1. Purpose

This charter establishes the governance structure, accountabilities, and operating cadence for MedCore Health Systems' AI risk management program. It defines who owns AI governance decisions, how those decisions are made, and how the program is sustained over time.

This charter operates under the **NIST AI RMF 1.0 GOVERN function** and is the authoritative reference for AI governance roles at MedCore. All AI policy documents, risk assessments, and operational procedures derive their authority from this charter.

---

## 2. Governance Mandate

MedCore Health Systems has determined that AI systems, including vendor-supplied clinical tools, administrative automation, and staff-initiated AI use, present material risks to patient privacy, clinical quality, and regulatory compliance. The organization is committed to governing AI use in a manner that:

- Protects patient safety and PHI as the primary obligation
- Enables staff to benefit from AI capabilities under appropriate oversight
- Maintains compliance with HIPAA, HITECH, and evolving federal AI guidance
- Aligns with the NIST AI Risk Management Framework 1.0
- Creates accountability for AI outcomes at every level of the organization

---

## 3. AI Governance Committee

### 3.1 Formation

MedCore establishes an **AI Governance Committee (AGC)** as the primary decision-making body for AI risk management. The AGC is a standing committee reporting to the Chief Executive Officer.

### 3.2 Membership

| Role | Committee Seat | Voting Rights |
|------|---------------|--------------|
| Chief Information Security Officer (CISO) | Chair | Yes |
| Privacy Officer | Standing member | Yes |
| Chief Medical Officer (CMO) or designee | Standing member | Yes |
| Chief Financial Officer (CFO) or designee | Standing member | Yes |
| IT Security Lead | Standing member | Yes |
| Clinical Operations Representative | Standing member | Yes |
| Administrative Operations Representative | Standing member | Yes |
| Legal Counsel | Advisory | No (advisory only) |
| AI Vendor Representatives | Ad hoc | No (invited as needed) |

Quorum requires five voting members including the CISO and Privacy Officer.

### 3.3 Authority

The AGC has authority to:

- Approve or reject AI system deployment requests
- Classify AI systems by risk tier
- Mandate remediation of identified AI risks
- Suspend or terminate use of any AI system pending risk review
- Approve exceptions to the AI Acceptable Use Policy (MC-POL-AI-001)
- Allocate AI governance budget and resources

Decisions requiring executive approval (budget above $50,000, vendor contract changes, regulatory disclosures) are escalated to the CEO.

---

## 4. Governance Cadence

### 4.1 Regular Meetings

| Meeting | Frequency | Participants | Purpose |
|---------|-----------|-------------|---------|
| AGC Full Meeting | Quarterly | All members | Risk register review, policy updates, new system approvals |
| CISO + Privacy Officer Sync | Monthly | CISO, Privacy Officer | Incident triage, Shadow AI findings, emerging regulatory changes |
| AI System Review | Semi-annual | AGC + system owners | Performance, drift, and control review for each authorized system |
| Emergency Session | As needed | CISO + quorum | AI security incidents, regulatory inquiries, urgent risk decisions |

### 4.2 Annual Activities

| Activity | Owner | Timing |
|----------|-------|--------|
| AI Risk Register full review | CISO + IT Security | Q1 |
| AI AUP review and update | Privacy Officer + CISO | Q1 |
| AI Vendor Assessment review | IT Security | Q2 |
| Staff AI Literacy Training refresh | HR + CISO | Q2 |
| NIST AI RMF self-assessment | CISO | Q3 |
| Board AI risk briefing | CISO | Q4 |

---

## 5. AI Risk Tier Classification

All AI systems used at MedCore are assigned a risk tier at intake. Tier determines oversight requirements.

| Tier         | Criteria                                                 | Examples                                     | Oversight Requirements                                             |
| ------------ | -------------------------------------------------------- | -------------------------------------------- | ------------------------------------------------------------------ |
| **Critical** | Unauthorized use, no BAA, PHI confirmed or likely        | Staff ChatGPT/Claude use with clinical notes | Immediate reporting, IT review within 24 hrs, potential suspension |
| **High**     | PHI exposure, clinical decision support, vendor with BAA | DiagnoAI Imaging Assistant                   | CISO approval, clinician HITL required, quarterly monitoring       |
| **Medium**   | Limited PHI, administrative automation, and BAA in place | PatientFlow Chatbot, AutoCode                | IT approval, CISO notification, semi-annual monitoring             |
| **Low**      | No PHI, no clinical impact, authorized use only          | Approved grammar/scheduling tools            | IT registration only, annual review                                |

---

## 6. AI System Lifecycle Governance

Every AI system at MedCore passes through the following lifecycle stages, each with defined governance touchpoints:

```
INTAKE → EVALUATION → APPROVAL → DEPLOYMENT → MONITORING → REVIEW → RETIRE/RENEW
```

| Stage | Owner | Key Activity | Documentation |
|-------|-------|-------------|---------------|
| Intake | Requesting staff/dept | Submit MC-FORM-AI-001 | Intake form |
| Evaluation | IT Security | Vendor assessment, BAA check, risk tier assignment | MC-VEN-AI-001 |
| Approval | AGC (or CISO for Low tier) | Risk acceptance decision | AGC meeting minutes |
| Deployment | IT Security + dept manager | Configuration, access controls, HITL setup | Deployment checklist |
| Monitoring | IT Security | Anomaly detection, usage logging, drift monitoring | Monthly reports |
| Review | AGC | Semi-annual system performance and control review | AGC meeting minutes |
| Retire/Renew | CISO | Decommission or re-approve for continued use | Retirement checklist |

---

## 7. Escalation Paths

| Trigger | First Escalation | Second Escalation | Timeline |
|---------|-----------------|------------------|----------|
| Suspected PHI in unauthorized AI | IT Security | Privacy Officer | Immediate (same day) |
| Confirmed PHI breach via AI | Privacy Officer + CISO | CEO + Legal | Within 1 hour |
| Shadow AI discovery | IT Security | Department Manager | Within 24 hours |
| AI system producing harmful clinical output | Clinician + CMO | CISO + Privacy Officer | Immediate |
| Vendor AI security incident | IT Security | CISO | Within 4 hours |
| Regulatory inquiry about AI | Legal + CISO | CEO | Within 2 hours |

---

## 8. Policy Hierarchy

This charter sits at the top of MedCore's AI governance document hierarchy:

```
MC-GOV-AI-002 (This Charter)
    ├── MC-POL-AI-001 (AI Acceptable Use Policy)
    ├── MC-GOV-AI-001 (RACI Matrix)
    ├── MC-INV-AI-001 (AI Use Case Inventory)
    ├── MC-RISK-AI-001 (AI Risk Register)
    ├── MC-XWALK-AI-001 (NIST AI RMF x HIPAA Crosswalk)
    ├── MC-RT-AI-001 (Red Team Playbook)
    ├── MC-IRP-AI-001 (AI Incident Response Addendum)
    ├── MC-FORM-AI-001 (AI System Intake Form)
    └── MC-VEN-AI-001 (AI Vendor Assessment Checklist)
```

---

## 9. Charter Review and Amendment

This charter is reviewed annually by the AGC and updated as needed following:

- Significant organizational change (merger, acquisition, major technology shift)
- Material regulatory change affecting AI governance obligations
- Significant AI security incident
- Changes to the NIST AI RMF or HIPAA guidance affecting governance requirements

Amendments require a vote of the AGC with quorum. Emergency amendments may be approved by the CISO and Privacy Officer jointly pending full AGC ratification at the next scheduled meeting.

---

## 10. References

| Document                      | Reference                         |
| ----------------------------- | --------------------------------- |
| NIST AI RMF 1.0               | airc.nist.gov/RMF                 |
| NIST AI RMF Playbook          | airc.nist.gov/Docs/1              |
| HIPAA Privacy Rule            | 45 CFR Part 164, Subpart E        |
| HIPAA Security Rule           | 45 CFR Part 164, Subparts A and C |
| HHS AI in Healthcare Guidance | hhs.gov                           |
| MC-POL-AI-001                 | AI Acceptable Use Policy          |
| MC-GOV-AI-001                 | RACI Matrix                       |

---

## Version History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | April 2026 | D'Arcy Bracken | Initial draft |

---

*MedCore Health Systems - Internal Use Only*
*MC-GOV-AI-002 v1.0 - AI Governance Charter*

[Back to Project Overview](AI%20Change%20Mgmt%20RMF%20-%20(Overview).md)
