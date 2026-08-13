# Compounding System Design


## Feedback Loops

| Loop | Input | Output | Compounds? | Status |
|------|-------|--------|-----------|--------|
| Recursive Learning | Human-reviewed verification decisions, confirmed fraud outcomes, false positives/negatives, and new gold-set cases | Better prompts/models, improved confidence thresholds, and more accurate verification decisions | Y | active |
| Cross-Domain Transfer | Fraud patterns and verified outcomes learned across different customer industries (e.g. payroll, procurement, real estate) | Transferable fraud signals and detection patterns that improve performance in new industries | Y | broken |
| Network Intelligence | Verification results and confirmed fraud signals aggregated across customers and accounts | Shared intelligence about suspicious accounts/payees, increasing detection accuracy across the customer network | Y | missing |

**Broken loop identified by partner:** Network intelligence is the biggest gap because fraud signals and verified outcomes are not yet aggregated across customers, meaning each customer’s learning largely benefits only themselves.
**Fix plan:** Create a shared fraud-intelligence layer that captures every confirmed fraud/verification outcome in a structured gold set, then expose anonymised signals back into future verification decisions.

## Context Connectivity
<!-- How does knowledge flow across teams and domains? Where does it silo? -->

**How knowledge flows:** Knowledge currently flows primarily through the central gold set and fraud/risk team, with human corrections feeding model evaluations and insights being transferred manually across customer industries.

**Where it silos:** Customer and domain data remains fragmented across accounts, teams, and workflows, with limited standardisation and sharing of outcomes preventing network-level intelligence from compounding.



## Governance Policy

**Scope:** AI-assisted bank-account and payee verification, including account ownership/name matching, fraud-risk scoring, anomaly detection, verification recommendations, confidence scoring, human escalation, audit logging, model evaluation, and the use of verified outcomes to improve the gold set and fraud models. Excludes: This policy does not authorize the AI to independently move funds, change customer payment instructions, make legally binding fraud accusations, override sanctions/AML controls, or make final decisions on high-risk payments without human approval; those remain governed by existing payments, compliance, legal, and operational policies.

**Autonomy boundaries:** Routine account verification with ≥90% confidence and no hard-risk signals, auto. Flagging an account as uncertain when confidence is 50–89%, auto. Blocking a payment based solely on an AI fraud assessment, human approval required. Moving funds, changing bank details, overriding sanctions/AML controls, or making a definitive fraud/legal determination, never auto.

**Escalation triggers:** 1. AI confidence <90% on the verification decision. 2. Payment exceeds the customer's predefined high-value threshold. 3. Account/bank details conflict with authoritative verification data. 4. Any confirmed or suspected fraud signal is detected. 5. Customer identity, legal entity, or beneficiary name cannot be reliably matched. 6. AI hallucination/error rate exceeds 0.5% in monitoring or evaluation. 7. Model drift exceeds 0.5% accuracy degradation per week or 2% over a rolling month.

**Audit cadence:** Real-time, Confidence scores, hard fraud signals, latency, model/provider failures and escalation triggers (James, AI Operations Lead). Daily, Human-reviewed cases, false positives/negatives, blocked payments and customer-impacting errors (Vanessa, Fraud Operations Manager). Weekly, Gold-set performance, hallucination rate, accuracy, drift velocity and provider/model performance (Charlotte, ML Risk Lead). Monthly, Model/prompt changes, bias by customer/domain, escalation volumes, COGS and provider performance (Daniel, Head of AI Risk & Governance). Quarterly, Full policy/control review, regulatory compliance, model risk assessment, vendor dependency and network-intelligence governance (Emma, Chief Risk Officer / AI Governance Committee).

**Regulatory exposure (EU AI Act / other):** EU AI Act, GDPR, UK GDPR/Data Protection Act 2018, and applicable financial-sector/model-risk regulations apply because the product processes potentially sensitive financial/personal data and influences payment-risk decisions.. Risk tier: high. Controls: Enterprise model-risk governance, DPIAs, data minimisation, encryption, role-based access, immutable audit logs, human-approval thresholds, continuous accuracy/hallucination/drift monitoring, gold-set testing, vendor-risk assessments, incident management, and controlled model deployment/rollback are in place, with high-impact payment decisions remaining subject to human oversight..

## Agent Topology

_Not shipping agents this version._


## Shadow AI Audit

Shadow AI Audit (user-side), Module 5

## Discover, User-Side Workarounds
- Users export verification results to ChatGPT/Claude to interpret ambiguous payee names and explain why an account was flagged. | source: Support ticket | signal: Capability gap | freq: H | spend: $150/mo | decision: Build
- Users manually combine your verification output with Excel/Google Sheets to create their own supplier risk scores and approval queues. | source: User interview | signal: Workflow gap | freq: H | spend: $250/mo | decision: Build
- Finance teams use Make/Zapier to connect your API to Slack/email and automatically alert managers when a high-risk account is detected. | source: Zapier/Make | signal: Workflow gap | freq: M | spend: $100/mo | decision: Partner
- Users query ChatGPT/Claude with invoice + supplier information to investigate suspicious bank-detail-change requests before contacting the supplier. | source: User interview | signal: Capability gap | freq: M | spend: $200/mo | decision: Build
- Users manually check Companies House / Google / supplier websites to validate whether a beneficiary is a legitimate business when your verification result is uncertain. | source: Sales call | signal: Trust gap | freq: M | spend: $300/mo | decision: Partner

## Pattern Assessment
- Workarounds found: 5
- Build candidates: 3
- Partner candidates: 2
- Ignore decisions: 0
- Adjacent spend: $1000/mo
- Dominant signal: Capability gap

## Action Plan
### Build
1. AI verification explanations and investigation — explain why an account is high/low risk and surface the relevant evidence.
2. Supplier risk scoring and approval queues — replace spreadsheet-based workflows with a native risk dashboard.
3. AI-assisted beneficiary investigation — combine verification signals with invoice/supplier context to help investigate ambiguous cases.

### Partner
1. Make/Zapier — provide official connectors so customers can trigger Slack/email/ERP workflows without building their own automation.
2. Business/entity data providers — integrate authoritative company-registration and business-verification data rather than forcing users to manually research suppliers.

### Ignore + Monitor
Do not build a generic spreadsheet replacement, generic ChatGPT interface, or generic Slack notification tool; monitor these behaviours because they are useful signals, but only absorb the underlying high-value verification/intelligence capability.

## Roadmap Brief
Based on your audit: 5 user-side workarounds discovered.
Decisions: 3 build · 2 partner · 0 ignore · 0 TBD.
Estimated adjacent spend: ~$1,000/mo across surveyed users.
Dominant signal: capability + workflow gaps.
Recommended next step: Prioritise native AI investigation/explanations and supplier-risk workflows, then validate the strongest external automation and business-data integrations with partnership teams.
Sequence the Build column by frequency × strategic relevance. Confirm Partner candidates with the external tools' partnership teams. Re-run this audit each quarter, as shadow-AI workarounds and user behaviour shift quickly.



