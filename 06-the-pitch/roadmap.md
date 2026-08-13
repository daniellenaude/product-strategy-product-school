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
We should invest now to make fraud investigation materially faster and more economical for our customers while turning the resulting verification decisions into a proprietary intelligence asset that is harder to replace than our current workflow.

**The case:**

1. Why now: Customer demand for AI-assisted fraud investigation is growing, customers are already creating shadow-AI workarounds, and competitors and AI providers are moving toward verification; waiting risks letting the workflow—and the data generated by it—move outside our product.
2. What's defensible: The defensible asset is not the AI model itself; it is the workflow and the fraud-intelligence data generated through human-reviewed verification decisions, confirmed fraud outcomes, and false positives/negatives. Today that moat is still a hypothesis—the strategy has not yet quantified the data flywheel or its rate of compounding—so the investment must prove that embedding investigation and risk decisions actually creates proprietary learning and switching costs.
3. The economics: The target is to move gross margin from approximately **30% to 80.8%**, but the strategy does not yet provide the underlying inference cost, pricing, AI-adjusted COGS, or stress-tested margin model needed to defend that number under 2–3× inference costs. The investment case therefore depends on validating both the margin improvement and a pricing model that captures the value created.

**The risks:**

1. Trust / failure modes: The front-page failure is a false negative that allows a fraudulent payment through. The proposed contract limits autonomous decisions to routine cases with ≥90% confidence and no hard-risk signals, escalates low-confidence/high-value/conflicting cases to humans, and targets <10% manual review; however, the golden dataset and full failure-mode coverage are not yet defined, so 95% reliability is not sufficient as the investment-grade risk metric.
2. Scale / governance: At 10× usage, the key risks are AI cost, model/provider failure, decision quality, and auditability. The strategy has real-time monitoring, audit logging, explicit autonomy boundaries and escalation triggers, but the governance design is incomplete around model-change controls, rollback, and the user-side shadow-AI audit.
3. Competitive: The kill scenario is that a platform or incumbent can reproduce the core verification capability without customers valuing our workflow or accumulated intelligence. The first test is therefore the H2 investigation workflow: **if we do not achieve at least a 30% reduction in median investigation time by week 6 without materially worsening decision accuracy, we stop**; the broader moat bet should also be killed if the product fails to generate meaningful workflow adoption and decision influence.

**The ask:**
Approve **$1.5–2.0M**, **6 engineers, 1 AI engineer, 1 PM and 1 designer**, with **12 weeks to MVP and 6 months to production**. In return, we get a production path for AI-assisted fraud investigation, authoritative-data enrichment and the workflow instrumentation needed to test the economic and data-moat thesis. If funded, we should explicitly trade off adjacent roadmap work—particularly the native supplier-risk dashboard—rather than adding this investment on top of the existing portfolio.

## M1 Baseline vs. Now
*Your 3-sentence AI strategy from Module 1 vs. what you'd say now:*

**M1 baseline:**
The product primarily relied on deterministic rules, third-party verification data, and manual review to assess bank account and payee risk. Ambiguous or complex cases required human investigation, creating slower workflows, higher operating costs, and limited scalability. Customer intelligence remained largely siloed, with limited ability to learn systematically from human corrections and verified fraud outcomes.
**Now:**
The product will introduce a tiered AI decisioning layer, using lightweight models for routine checks and stronger models for ambiguous or high-risk cases, with humans retaining control of consequential decisions. AI will automate investigation, explain verification decisions, and surface fraud signals, improving speed and reducing manual effort while maintaining strict accuracy, hallucination, and confidence thresholds. Every human correction and confirmed fraud outcome will feed the gold set and network intelligence layer, creating a compounding data advantage that improves the product as usage grows.
