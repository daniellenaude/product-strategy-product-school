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

**Scope:**
**Autonomy boundaries:**
**Escalation triggers:**
**Audit cadence:**
**Regulatory exposure (EU AI Act / other):**

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
