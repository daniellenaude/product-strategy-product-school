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


## Agent Topology
<!-- If using agents: what can each agent do? What can't it do? Who approves what? -->

## Shadow AI Audit

| Tool | Owner | Risk Level | Decision |
|------|-------|-----------|----------|
| | | H / M / L | keep / govern / kill |
| | | H / M / L | keep / govern / kill |
| | | H / M / L | keep / govern / kill |

**Total tools found:**
**Tools after triage:**
**Estimated hidden spend:**
