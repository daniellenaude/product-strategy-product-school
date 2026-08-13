# Three-Horizon Roadmap & Board Pitch

## Roadmap

### Horizon 1, Ship (0–4 weeks)

| Initiative                                                                                                          | Strategy Component | Why it ships now                                                                                                                                                                                                             | Confidence |
| ------------------------------------------------------------------------------------------------------------------- | ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| **3. Launch Make/Zapier integrations** — automatically push high-risk alerts into Slack                             | **Guardrails**     | Relatively low-complexity workflow integration that extends existing escalation/alerting without changing the core AI decision. It operationalises the existing risk signals rather than introducing a new model dependency. | H          |
| **4. Integrate authoritative business-data sources** — enrich uncertain beneficiary checks with company/entity data | **Contract**       | Directly improves verification evidence for ambiguous cases and can reduce unnecessary manual research. It strengthens the existing confidence + HITL architecture using authoritative external evidence.                    | H          |

### Horizon 2, Validate (1–3 months)

| Initiative                                                                                   | Strategy Component | Hypothesis                                                                                                                                                                                 | Kill Criteria                                                                                                                                            | Confidence |
| -------------------------------------------------------------------------------------------- | ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| **2. Build AI investigation workflow** — investigate ambiguous payees using invoices         | **Contract**       | Giving investigators an AI-assisted evidence-gathering workflow will reduce time-to-resolution for ambiguous cases while maintaining or improving decision quality.                        | **If we don't see ≥30% reduction in median investigation time by week 6, with no material deterioration in investigation accuracy, we stop.**            | M          |
| **1. Build native supplier risk dashboard** — replace spreadsheet workflows with risk scores | **Moat**           | Embedding supplier-risk decisions in the product will increase workflow depth, generate proprietary decision/outcome data, and create switching costs beyond the underlying AI capability. | **If we don't see ≥25% weekly active usage among pilot customers and evidence that risk-score outputs influence supplier decisions by week 6, we stop.** | M          |

### Horizon 3, Explore (3–6 months)

| Initiative          | Strategy Component | What must be true first                                                                                       | Confidence |
| ------------------- | ------------------ | ------------------------------------------------------------------------------------------------------------- | ---------- |
| **None currently.** | —                  | The backlog has no genuine H3 experiment. That is a strategic gap given the stated platform-replication risk. | L          |

### Unmapped (cut or rethink)

| Initiative | Why it's unmapped                                                    | Recommendation |
| ---------- | -------------------------------------------------------------------- | -------------- |
| **None**   | All four initiatives connect to at least one of the five components. | —              |

### Mapping Disagreements

No disagreements, all user mappings stand. **No explicit `[User-mapped to: X]` mappings were included in the backlog, so all four mappings above are my classifications.**

**(a)** You are over-indexed on **H1/H2 execution** and have no H3 exploration; what's missing is a small portfolio of experiments aimed specifically at discovering a durable platform/data moat.
**(b)** If budget got cut, I'd protect **the AI investigation workflow** as the strongest near-term test of whether AI materially improves the high-stakes verification workflow rather than merely adding surface-level features.
**(c)** **Kill the native supplier risk dashboard today** unless supplier risk is explicitly part of the core bank-account/payee-verification bet; it risks becoming an adjacent product that consumes roadmap capacity without strengthening the stated strategic thesis.


## Board Pitch

**Thesis (1 sentence):**

**The case:**
1. Why now:
2. What's defensible:
3. The economics:

**The risks:**
1. Trust / failure modes:
2. Scale / governance:
3. Competitive:

**The ask:**

## M1 Baseline vs. Now
*Your 3-sentence AI strategy from Module 1 vs. what you'd say now:*

**M1 baseline:**

**Now:**
