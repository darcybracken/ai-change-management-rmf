---
document-id: MC-VEN-AI-002
framework: "NIST AI RMF 1.0 - GOVERN 1.4, MAP 3.5, MEASURE 2.7"
regulatory: "HIPAA 45 CFR 164.308(b)"
version: 1.0
status: complete
assessment-subject: Microsoft Azure OpenAI Service
use-case: PatientFlow LLM-powered patient intake and scheduling chatbot
recommendation: Conditional Approval
---

# MC-VEN-AI-002 - AI Vendor Assessment: Azure OpenAI Service

**MedCore Health Systems**
*Completed Assessment -Assessed by: D'Arcy Bracken, IT Security*


**Assessment scope**
This assessment evaluates Microsoft Azure OpenAI Service (text-based endpoints) as the LLM backend for the proposed PatientFlow patient intake and scheduling chatbot. Scope is limited to text-based completions endpoints only. Azure OpenAI Realtime API (audio in/out) is excluded from this assessment, as that capability remains in preview and is not HIPAA-eligible as of the assessment date.

---

## Vendor Information

| Field                       | Response                                                           |
| --------------------------- | ------------------------------------------------------------------ |
| Vendor name                 | Microsoft Corporation                                              |
| AI product name and version | Azure OpenAI Service (GPT-4o, text completions endpoints)          |
| Assessment date             | 2026-06-13                                                         |
| Assessed by                 | D'Arcy Bracken, IT Security                                        |
| Intake form reference       | MC-FORM-AI-001 - PatientFlow submission                            |
| Risk tier (from intake)     | Medium (demographics, symptoms; no imaging or full clinical notes) |

---

## Section A -- Legal and Contractual

| #    | Requirement                                                                   | Status | Notes                                                                                                                                                                                                                                                                                    |
| ---- | ----------------------------------------------------------------------------- | ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| A-01 | Business Associate Agreement (BAA) available and reviewed by Legal            | Pass   | BAA is included by default in the Microsoft Online Services Data Protection Addendum (DPA) for Enterprise Agreement and CSP customers. No separate BAA signature is required for coverage, it is automatic under a qualifying license. Legal confirmed coverage applies to MedCore's EA. |
| A-02 | BAA covers all PHI processing activities for this use case                    | Pass   | Azure OpenAI (text endpoints) is explicitly HIPAA-eligible under the Microsoft BAA. Preview features, and non-text endpoints (DALL-E, Realtime API) are excluded, none of which are in the PatientFlow scope.                                                                            |
| A-03 | Vendor data processing agreement (DPA) reviewed                               | Pass   | Microsoft Online Services DPA reviewed by Legal. DPA confirms prompts and completions are not shared with OpenAI and are not used to train Microsoft or third-party models.                                                                                                              |
| A-04 | Vendor ToS does not permit use of MedCore inputs to train models              | Pass   | Confirmed: customer prompts and completions are NOT used to train Microsoft or OpenAI base models without explicit opt-in. Data remains private to the MedCore tenant.                                                                                                                   |
| A-05 | Data residency requirements met (US-based for HIPAA PHI)                      | Pass   | Azure region selection allows US-only data residency. PatientFlow deployment must be configured to East US or West US 2 region. IT Security to enforce via Azure Policy at deployment.                                                                                                   |
| A-06 | Vendor breach notification obligations defined in BAA (60-day HIPAA timeline) | Pass   | Microsoft BAA includes breach notification obligations. Microsoft notifies covered entities without unreasonable delay, as required by HIPAA.                                                                                                                                            |
| A-07 | Vendor liability and indemnification terms reviewed by Legal                  | Pass   | Standard Microsoft EA terms reviewed. Legal note: indemnification is limited, MedCore retains primary liability for HIPAA compliance as a covered entity.                                                                                                                                |
| A-08 | Termination and data return/destruction provisions in contract                | Pass   | DPA includes data deletion provisions upon contract termination. The Zero Data Retention (ZDR) option available for approved deployments eliminates post-processing data retention.                                                                                                      |

**Section A result:** Pass

---

## Section B - Security Posture

| #    | Requirement                                                       | Status      | Notes                                                                                                                                                                                                                                                     |
| ---- | ----------------------------------------------------------------- | ----------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| B-01 | SOC 2 Type II report obtained and reviewed (within 12 months)     | Pass        | Azure SOC 2 Type II attestation is current. Reports available via Microsoft Service Trust Portal (servicetrust.microsoft.com). IT Security to download current report and file.                                                                           |
| B-02 | Vendor publishes security whitepaper or trust center              | Pass        | Microsoft Azure Trust Center and Service Trust Portal document security controls, compliance certifications, and audit reports. Responsible AI Transparency Report published annually (2025 report available).                                            |
| B-03 | Data encryption in transit (TLS 1.2+) confirmed                   | Pass        | All Azure OpenAI API calls use TLS 1.2 minimum. Enforced at the API gateway level, it cannot be downgraded by client configuration.                                                                                                                       |
| B-04 | Data encryption at rest confirmed                                 | Pass        | FIPS 140-2 compliant 256-bit AES encryption at rest. Microsoft-managed keys by default, the customer-managed key (CMK) option is available via Azure Key Vault for higher-sensitivity deployments.                                                        |
| B-05 | Multi-factor authentication available for admin access            | Pass        | Azure Entra ID (formerly Azure AD) enforces MFA for all administrative access. MedCore must configure the Conditional Access policy to require MFA for the PatientFlow service account.                                                                   |
| B-06 | Access control: role-based access for MedCore staff               | Pass        | Azure RBAC applies to all OpenAI resource access. The principle of least privilege must be enforced at deployment. The PatientFlow service identity should be scoped to inference only, not to resource management.                                       |
| B-07 | Vendor penetration testing conducted annually (evidence provided) | Pass        | Microsoft conducts annual third-party penetration testing against Azure infrastructure. Results are not shared publicly, but penetration testing attestation is available via the Service Trust Portal under NDA.                                         |
| B-08 | Vendor vulnerability disclosure / CVE program exists              | Pass        | Microsoft Security Response Center (MSRC) operates a documented vulnerability disclosure program, including a bug bounty. Azure OpenAI is in scope.                                                                                                       |
| B-09 | Vendor incident response process documented and shared            | Pass        | Microsoft publishes its incident response framework. Contractual notification obligations are in the DPA. MedCore will receive notification if a Microsoft-side incident affects MedCore data.                                                            |
| B-10 | Vendor subprocessor list reviewed (who else touches MedCore data) | Conditional | Microsoft publishes an online services subprocessor list. For Azure OpenAI text endpoints, OpenAI LLC is NOT a subprocessor, prompts do not flow to OpenAI infrastructure. MedCore must verify the current subprocessor list at deployment and quarterly. |

**Section B result:** Conditional - B-10 requires ongoing subprocessor monitoring; MedCore to add to quarterly review calendar.

---

## Section C - AI-Specific Provenance and Safety

| #    | Requirement                                                                           | Status      | Notes                                                                                                                                                                                                                                                                                                                                      |
| ---- | ------------------------------------------------------------------------------------- | ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| C-01 | Model card or equivalent documentation available                                      | Pass        | Microsoft publishes Responsible AI documentation including model overview, intended uses, limitations, and safety evaluations for each model family in the Azure AI Foundry portal and on learn.microsoft.com.                                                                                                                             |
| C-02 | Training data sources disclosed or described                                          | Conditional | Microsoft describes training data at a high level (internet text, licensed data, proprietary data) but does not disclose specific datasets or training data provenance at the level that would satisfy a comprehensive supply chain audit. This is consistent with industry practice but represents a gap vs. MC-VEN-AI-001 C-02 criteria. |
| C-03 | Known limitations and failure modes documented                                        | Pass        | Microsoft publishes documented limitations including hallucination behavior, knowledge cutoff dates, potential for biased outputs, and context window constraints. The Responsible AI overview explicitly states that the system "may produce inaccurate or unreliable information."                                                       |
| C-04 | Bias and fairness testing documented                                                  | Pass        | Microsoft's 2025 Responsible AI Transparency Report documents bias evaluation methodology, including red teaming, fairness assessments, and mitigation approaches. Reports are published annually.                                                                                                                                         |
| C-05 | Vendor discloses model update / retraining cadence                                    | Conditional | Azure OpenAI documents model version availability and deprecation schedules. However, minor model updates within a version may occur without explicit notification. MedCore must pin PatientFlow to a specific model version and implement a change notification workflow.                                                                 |
| C-06 | Vendor provides notification of significant model changes                             | Conditional | Model deprecation notices are published on learn.microsoft.com with at least 30 days' advance notice. MedCore must subscribe to Azure service health notifications and assign a reviewer.                                                                                                                                                  |
| C-07 | Vendor provides accuracy benchmarks relevant to MedCore use case                      | Conditional | Microsoft publishes general benchmarks (MMLU, HellaSwag, etc.) but no healthcare-specific accuracy data for patient intake use cases. MedCore must conduct its own PatientFlow accuracy validation before authorization.                                                                                                                   |
| C-08 | Vendor documents adversarial testing / red team methodology                           | Pass        | Microsoft documents its AI Red Team program and publishes its findings in the Responsible AI Transparency Report. The team conducts adversarial testing, including prompt-injection evaluations across model families.                                                                                                                     |
| C-09 | Vendor has AI ethics or responsible AI policy published                               | Pass        | Microsoft's Responsible AI Standard and Principles are publicly published. The 2025 Transparency Report describes implementation.                                                                                                                                                                                                          |
| C-10 | HITL is technically feasible with this system (outputs can be reviewed before action) | Pass        | Azure OpenAI is an API-based inference service. PatientFlow's application layer controls whether outputs are surfaced to staff for review before action. HITL is an application design requirement, not a vendor constraint. MedCore's PatientFlow architecture must enforce HITL at the application layer.                                |

**Section C result:** Conditional - four items require MedCore mitigation action (C-02, C-05, C-06, C-07). None are vendor failures; all are standard limitations for commercial LLM APIs.

---

## Section D - HIPAA Compliance Verification

| #    | Requirement                                                          | Status      | Notes                                                                                                                                                                                                                                                                                                                                                |
| ---- | -------------------------------------------------------------------- | ----------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| D-01 | Vendor explicitly represents HIPAA compliance for covered entity use | Pass        | Microsoft explicitly states Azure OpenAI text-based endpoints are HIPAA-eligible services covered under the Microsoft BAA. This representation is in the DPA and the Azure compliance documentation.                                                                                                                                                 |
| D-02 | Vendor's PHI handling documented (where stored, how long retained)   | Pass        | Prompts and completions are processed within the selected Azure region. Default retention for abuse monitoring is 30 days, the Zero Data Retention (ZDR) option eliminates this. MedCore should request ZDR approval for PatientFlow due to PHI involvement.                                                                                         |
| D-03 | Vendor data retention and deletion policy documented                 | Pass        | Documented in DPA. ZDR available. Upon contract termination, Microsoft deletes customer data in accordance with the documented retention schedule.                                                                                                                                                                                                   |
| D-04 | Audit logging of PHI access available to MedCore                     | Pass        | Azure Monitor and Azure Diagnostic Logs provide API call logging. MedCore must configure log retention and route logs to its SIEM. PatientFlow must log all inference calls with timestamps and session IDs (not raw PHI) for audit purposes.                                                                                                        |
| D-05 | Vendor workforce trained on PHI handling                             | Pass        | Microsoft states that workforce members handling customer data receive HIPAA awareness training as part of the enterprise compliance program. Documented in Microsoft's compliance framework.                                                                                                                                                        |
| D-06 | Vendor provides right to audit (or accepts third-party audit)        | Conditional | Microsoft does not grant individual customer audit rights to Azure infrastructure. Instead, Microsoft provides third-party audit reports (SOC 2, ISO 27001, FedRAMP) via the Service Trust Portal as the audit mechanism. This is standard for hyperscale cloud providers and is accepted under HIPAA BAA terms. Legal confirmed this is acceptable. |

**Section D result:** Pass with note - D-06 limitation is expected and contractually acceptable. ZDR request recommended before authorization.

---

## Section E - Operational Requirements

| #    | Requirement                                                     | Status      | Notes                                                                                                                                                                                                                                                                                                                                 |
| ---- | --------------------------------------------------------------- | ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| E-01 | Uptime SLA documented and acceptable for clinical use           | Pass        | Azure OpenAI Service SLA is 99.9% monthly uptime for production deployments. PatientFlow is scheduling/intake, not life-critical, so 99.9% is acceptable. Clinical staff can handle scheduling manually during downtime.                                                                                                              |
| E-02 | Vendor support SLA documented                                   | Pass        | Microsoft Premier Support or Unified Support is available. MedCore's existing Azure support tier should be confirmed as covering Azure OpenAI resources before deployment.                                                                                                                                                            |
| E-03 | Disaster recovery / business continuity plan documented         | Pass        | Azure publishes documentation on regional redundancy and availability zones. PatientFlow should be deployed to a region that supports availability zones. The manual scheduling process must be documented in the PatientFlow runbook.                                                                                                |
| E-04 | Exit / migration plan feasible if vendor relationship ends      | Conditional | Azure OpenAI uses OpenAI-compatible API endpoints. Migration to another Azure-hosted model or alternative provider is technically feasible. However, PatientFlow's prompts, fine-tuning (if any), and evaluation data must be documented and exportable. IT Security requires an exportable prompt library as a deployment condition. |
| E-05 | API documentation complete for integration with MedCore systems | Pass        | Azure OpenAI API documentation is comprehensive and publicly available on learn.microsoft.com. REST API and SDK support for Python, .NET, and JavaScript. PatientFlow integration is technically well-supported.                                                                                                                      |

**Section E result:** Conditional - E-04 requires documented exit plan before authorization.

---

## Overall Assessment

| Section                    | Result         | Critical Gaps                                                                                                              |
| -------------------------- | -------------- | -------------------------------------------------------------------------------------------------------------------------- |
| A - Legal / Contractual    | Pass           | None                                                                                                                       |
| B - Security Posture       | Conditional    | Subprocessor list requires quarterly monitoring (B-10)                                                                     |
| C - AI Provenance / Safety | Conditional    | Training data opacity (C-02), model version pinning required (C-05, C-06), MedCore must run own accuracy validation (C-07) |
| D - HIPAA Compliance       | Pass with note | ZDR request recommended before authorization                                                                               |
| E - Operational            | Conditional    | Exit plan and prompt library export required (E-04)                                                                        |

**Overall recommendation:**

- [ ] Approve
- [ ] **Conditional Approval** - All critical HIPAA requirements (BAA, encryption, data residency, PHI handling) are met. Conditional items are standard limitations of commercial LLM APIs and are mitigable through MedCore configuration and process controls. Authorization may proceed subject to all conditions below being satisfied.
- [ ] Reject

---

## Conditions of Authorization

All conditions must be satisfied before PatientFlow receives authorization to process PHI via Azure OpenAI Service:

| #      | Condition                                                                                            | Owner             | Deadline             |
| ------ | ---------------------------------------------------------------------------------------------------- | ----------------- | -------------------- |
| CON-01 | Deploy to US-only Azure region; enforce via Azure Policy                                             | IT Security       | Before deployment    |
| CON-02 | Submit a Zero Data Retention (ZDR) request to Microsoft                                              | IT Security       | Before deployment    |
| CON-03 | Pin PatientFlow to a specific Azure OpenAI model version, document change notification workflow      | IT Security       | Before deployment    |
| CON-04 | Subscribe to Azure service health notifications, assign reviewer                                     | IT Security       | Before deployment    |
| CON-05 | Conduct PatientFlow accuracy validation for patient intake use case before authorization             | CMO + IT Security | Before authorization |
| CON-06 | Configure Azure Monitor logging for all PatientFlow inference calls, route to SIEM                   | IT Security       | Before deployment    |
| CON-07 | Enforce HITL at the PatientFlow application layer, no AI output triggers action without staff review | IT Security + CMO | Before deployment    |
| CON-08 | Document PatientFlow manual fallback procedure for Azure outage                                      | IT Security       | Before deployment    |
| CON-09 | Document and export PatientFlow prompt library, verify data portability for exit scenario            | IT Security       | Before authorization |
| CON-10 | Add Azure OpenAI subprocessor list to quarterly review calendar                                      | IT Security       | Before authorization |
| CON-11 | Confirm MedCore Azure support tier covers Azure OpenAI resources                                     | IT Security       | Before deployment    |
| CON-12 | MedCore to conduct PatientFlow-specific red team testing per MC-RT-AI-001 (PF-001 through PF-006)    | IT Security       | Before authorization |

---

**Scope reminder**

This assessment covers Azure OpenAI Service text-based completions endpoints only. If PatientFlow is later extended to use voice input, audio output, image processing, or any preview-tier feature, a supplemental assessment is required before those capabilities process PHI.

---

**IT Security reviewer:** D'Arcy Bracken **Date:** 2026-06-13

**Privacy Officer reviewer (required for PHI-processing systems):** _________________________ **Date:** _____________

**CISO sign-off:** _________________________ **Date:** _____________

---

*MedCore Health Systems - Internal Use Only*
*MC-VEN-AI-002 v1.0 - Azure OpenAI Service Vendor Assessment*

[Blank Template (MC-VEN-AI-001)](AI%20Vendor%20Assessment%20Checklist.md) | [AI Inventory](AI%20Use%20Case%20Inventory.md) | [Project Overview](AI%20Change%20Mgmt%20RMF%20-%20(Overview).md)
