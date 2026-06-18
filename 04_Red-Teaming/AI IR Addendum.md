---
document-id: MC-IRP-AI-001
framework: NIST AI RMF 1.0 - MANAGE 4.1
regulatory: HIPAA 45 CFR 164.308(a)(6); HITECH 13402
version: 1
status: draft
parent_document: MC-IRP-001 (MedCore Incident Response Plan)
---

# MC-IRP-AI-001 - AI Incident Response Addendum

**MedCore Health Systems**
*Internal Security Document - Version 1.0*

**Scope**

This addendum extends MedCore's existing Incident Response Plan (MC-IRP-001) with AI-specific response procedures. It does not replace the core IRP. For all phases not covered here (general containment, forensics, communication), refer to MC-IRP-001.

---

## AI Incident Categories

| Category | Description | Examples |
|----------|-------------|---------|
| **PHI-AI-01** | PHI disclosed via unauthorized AI system | Staff pasting patient notes into ChatGPT |
| **PHI-AI-02** | PHI disclosed via authorized AI system failure | DiagnoAI transmitting PHI to unauthorized endpoint |
| **INJ-AI-01** | Prompt injection attack on patient-facing AI | Adversarial input in PatientFlow intake form |
| **CLN-AI-01** | AI clinical safety failure | DiagnoAI false negative on significant finding |
| **VEN-AI-01** | AI vendor security incident | Vendor breach affecting MedCore AI system |
| **SHA-AI-01** | Shadow AI discovery | IT discovers unauthorized LLM use with PHI |

---

## Response Procedures by Category

### PHI-AI-01 - PHI via Unauthorized AI (Shadow AI)

**Trigger:** Staff disclosure, IT discovery, or anomaly report indicating PHI entered into an unauthorized AI system.

| Phase         | Action                                                                                                                     | Owner                         | Timeline           |
| ------------- | -------------------------------------------------------------------------------------------------------------------------- | ----------------------------- | ------------------ |
| Detection     | IT Security notified, incident ticket opened                                                                               | IT Security                   | Immediate          |
| Containment   | Interview disclosing staff, document what PHI was entered, into which system, on what date                                 | IT Security + Privacy Officer | Within 24 hours    |
| Assessment    | Privacy Officer conducts HIPAA breach notification analysis per 45 CFR 164.402                                             | Privacy Officer               | Within 72 hours    |
| Notification  | If breach threshold met: notify affected patients within 60 days, notify HHS OCR annually (or immediately if 500+ records) | Privacy Officer + Legal       | Per HIPAA timeline |
| Remediation   | Non-punitive conversation with staff, document self-disclosure, and assign AI literacy training                            | HR + Department Manager       | Within 1 week      |
| Post-incident | Update Shadow AI Discovery Report, assess whether enterprise LLM alternative should be expedited                           | CISO                          | Within 2 weeks     |


**HIPAA Breach Notification Timeline**

The HIPAA Breach Notification Rule (45 CFR 164.404) requires notification to affected individuals within **60 days** of discovery. For breaches affecting 500+ individuals, HHS OCR must be notified **immediately** (same 60-day window). For smaller breaches, HHS OCR is notified annually. Do not delay the Privacy Officer assessment the 60-day clock starts at discovery, not at assessment completion.

---

### INJ-AI-01 - Prompt Injection Attack (Patient-Facing AI)

**Trigger:** Output anomaly monitor alert (Critical severity) staff report of unexpected AI behavior, red team finding in production.

| Phase               | Action                                                                                                              | Owner                         | Timeline                   |
| ------------------- | ------------------------------------------------------------------------------------------------------------------- | ----------------------------- | -------------------------- |
| Detection           | Critical anomaly alert fires, IT Security investigates                                                              | IT Security                   | Within 1 hour of alert     |
| Containment         | Suspend patient-facing AI session, preserve logs, do not clear system cache                                         | IT Security                   | Within 1 hour              |
| Analysis            | Review full conversation log, determine injection vector, assess whether PHI was disclosed or clinical action taken | IT Security + Privacy Officer | Within 4 hours             |
| Escalation          | If PHI disclosed: PHI-AI-02 response activated. If clinical action taken: CLN-AI-01 response activated              | CISO                          | Per assessment             |
| Vendor notification | Notify AI vendor of attack vector, request patch or configuration fix                                               | IT Security + CISO            | Within 24 hours            |
| Remediation         | Update red team test case library with new attack vector, re-test before restoring service                          | IT Security                   | Before service restoration |
| Post-incident       | Update false negative rate tracking, assess output anomaly monitor coverage gap                                     | IT Security                   | Within 1 week              |

---

### CLN-AI-01 - AI Clinical Safety Failure

**Trigger:** Physician reports incorrect AI clinical output, patient adverse event related to AI recommendation, internal audit discovers AI error in clinical documentation.

| Phase            | Action                                                                                                                  | Owner                      | Timeline           |
| ---------------- | ----------------------------------------------------------------------------------------------------------------------- | -------------------------- | ------------------ |
| Detection        | Clinician or patient safety officer reports to CMO + CISO                                                               | CMO + CISO                 | Immediate          |
| Patient safety   | CMO assesses whether patient was harmed, activates clinical incident response if needed                                 | CMO                        | Immediate          |
| AI system        | Suspend AI system pending review, preserve all logs and outputs                                                         | IT Security                | Within 2 hours     |
| Root cause       | Determine whether failure was model error, input error, HITL bypass, or drift                                           | IT Security + Vendor + CMO | Within 48 hours    |
| Regulatory       | Assess whether clinical AI failure implicates FDA (Software as a Medical Device) or Joint Commission reporting          | Legal + CMO                | Within 72 hours    |
| Vendor           | Issue corrective action notice to vendor, require root cause analysis and remediation plan                              | CISO + Legal               | Within 1 week      |
| Re-authorization | System must pass red team re-testing before redeployment, CMO clinical validation re-run if significant accuracy change | CMO + CISO                 | Before restoration |

**SaMD Note**

AI diagnostic imaging tools (DiagnoAI) may be classified as **Software as a Medical Device (SaMD)** under FDA jurisdiction. Clinical failures in SaMD systems may require FDA Medical Device Reporting (MDR) in addition to internal incident response. Legal and CMO must assess FDA applicability at initial deployment and at any significant clinical failure.

---

### VEN-AI-01 - AI Vendor Security Incident

**Trigger:** Vendor notifies MedCore of security breach, IT Security discovers anomalous vendor system behavior; third-party breach report names MedCore's vendor.

| Phase                 | Action                                                                                | Owner                         | Timeline           |
| --------------------- | ------------------------------------------------------------------------------------- | ----------------------------- | ------------------ |
| Detection             | Vendor notification or IT discovery                                                   | IT Security                   | Immediate          |
| Verification          | Confirm breach scope, determine whether MedCore PHI is affected                       | IT Security + Privacy Officer | Within 4 hours     |
| Containment           | Suspend integration with affected vendor system; revoke API keys                      | IT Security                   | Within 4 hours     |
| BAA review            | Review BAA for vendor breach notification obligations and MedCore's rights            | Privacy Officer + Legal       | Within 24 hours    |
| HIPAA assessment      | If MedCore PHI affected: PHI-AI-02 response, Privacy Officer breach assessment        | Privacy Officer               | Per HIPAA timeline |
| Vendor accountability | Issue a formal incident inquiry to the vendor, request a third-party forensics report | CISO + Legal                  | Within 48 hours    |
| Re-authorization      | Vendor must provide remediation evidence before MedCore restores integration          | CISO                          | Before restoration |

---

## Communication Templates

### Internal Notification (Shadow AI Discovery)

```
TO: [Department Manager]
FROM: IT Security
SUBJECT: AI Security Notification - Action Required

We have identified potential unauthorized AI tool use within your department.
This is not a punitive communication. MedCore's non-punitive disclosure policy
applies to all staff who come forward voluntarily.

We need to schedule a brief, confidential conversation with you to:
1. Understand what tools were used and what information was entered
2. Determine whether any patient information may have been affected
3. Connect affected staff with the AI literacy training resources

Please contact IT Security at [ai-safety@medcorehealthsystems.org] within 24 hours.

This communication is confidential and should not be shared with other staff
pending our conversation.
```

### Patient Notification (PHI Breach Template)

```
Dear [Patient Name],

We are writing to inform you that MedCore Health Systems recently discovered
that some of your health information may have been inadvertently shared with
an unauthorized third-party service.

What happened: [Brief factual description of the incident]
What information was involved: [Specific PHI categories]
What we are doing: [Remediation steps taken]
What you can do: [Any patient action if applicable]

We take the privacy of your health information seriously and sincerely apologize
for this incident. If you have questions, please contact our Privacy Officer at
[privacy@medcorehealthsystems.org] or [phone number].

Sincerely,
[Privacy Officer name and title]
MedCore Health Systems
```

---

## Version History

| Version | Date       | Author         | Changes                                                                                  |
| ------- | ---------- | -------------- | ---------------------------------------------------------------------------------------- |
| 1.0     | April 2026 | D'Arcy Bracken | Initial addendum - five incident categories response procedures; communication templates |

---

*MedCore Health Systems - Confidential Internal Use Only*
*MC-IRP-AI-001 v1.0 - AI Incident Response Addendum*

[Back to Project Overview](AI%20Change%20Mgmt%20RMF%20-%20(Overview).md) | [Red Team Playbook](Red%20Team%20Playbook.md) | [Risk Register](AI%20Risk%20Register.md)
