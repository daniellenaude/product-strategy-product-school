# Cost Curve & Pricing Strategy

## Packaging Decision
Leader feature: Instant bank account verification that helps businesses stop fraudulent payments before money is sent.
Filler feature: Basic account validation, audit logs, dashboards, and API integrations that customers expect from any fintech tool.
Killer feature: AI-powered fraud intelligence that detects suspicious payees using proprietary payment outcomes and network signals before a payment is approved.
Usage of killer feature: Finance teams use it on every outbound payment to automatically block or flag high-risk bank accounts before funds leave the business. Therefore roughly 25% and should be an add-on.


## Cost Model

| Cost Category | Per-User/Month | Notes |
|--------------|----------------|-------|
| Inference (primary model) |$3.50 |Claude/GPT for fraud reasoning and risk explanations on every verification request. |
| Inference (cascading/triage) |$0.75 |Use a smaller, cheaper model for ~70–80% of requests; escalate only ambiguous cases to the primary model. |
| Infrastructure |$2.00 |API gateway, compute, monitoring, logging, queues, and orchestration. |
| Data/storage |$4.50 |Verification history, embeddings, audit logs, fraud signals, and encrypted storage. |
| Human-in-the-loop |$1.75 |Manual review of approximately 1–2% of high-risk or disputed cases. |
| **Total AI COGS** |$12.00 |Total AI-related operating cost per customer per month. |

## Cascading Strategy
<!-- Cheap model → frontier model routing logic -->

**Triage model: Claude 4.5 Haiku = fast, low-cost classification of routine verification requests **
**Frontier model: Claude Sonnet 4/Opus 5 = complex fraud investigations, ambiguous account ownership cases, and generating customer-facing risk explanations **
**Routing rule: Send every request to the triage model first, escalating only uncertain, high-risk, or high-value payments to the frontier model **

| Feature | Complexity | Model Tier | Cost/Request | Volume % | Weighted | 
|---------|------------|------------|--------------|----------|----------|
|Bank Account Verification |Low |Triage |$0.01 |70% |$0.007 |
|Payee Risk Assessment |Medium |Frontier (Sonnet 4) |$0.05 |20% |$0.01 |
|Fraud Investigation and Explanation |High |Frontier (Opus 5) |$0.25 |10% |$0.025 |
|Blended | | | | 100% | $0.042 |

**Expected cascade ratio: 70-20-10 **

## Pricing Model

**Current pricing:**
**Proposed AI pricing:**
**Model:** seat-based / usage-based / outcome-based / hybrid

## Stress Tests

| Scenario | Impact on Margin | Response |
|----------|-----------------|----------|
| Inference costs 3x | | |
| Heaviest segment doubles | | |
| Model provider raises prices 50% | | |

## Board One-Pager
<!-- Before/After: Old SaaS revenue vs. AI usage revenue for your product -->

**Before (traditional SaaS):**
**After (AI-enabled):**
**Net margin shift:**
