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
**Frontier model: Claude Opus 5 = complex fraud investigations, ambiguous account ownership cases, and generating customer-facing risk explanations **
**Routing rule: Send every request to the triage model first, escalating only uncertain, high-risk, or high-value payments to the frontier model **

| Feature | Complexity | Model Tier | Cost/Request | Volume % | Weighted | 
|---------|------------|------------|--------------|----------|----------|
|Bank Account Verification |Low |Triage |$0.01 |70% |$0.007 |
|Payee Risk Assessment |Medium |Mid (Claude Sonnet 4) |$0.05 |20% |$0.01 |
|Fraud Investigation and Explanation |High |Frontier |$0.25 |10% |$0.025 |
|Blended | | | | 100% | $0.042 |

**Expected cascade ratio: 70-20-10 **

## Pricing Model

**Current pricing: n/a **
**Proposed AI pricing:

Pricing Strategy
- Strategy posture: Maximize
- Pricing model: Seat / Access
- Unit of work metered: bank account verification requests
- Base fee ($/month): 199
- Price per unit: $0.15
- Estimated units/user/month: 2000
- Implied revenue/user/month: $499.00

Decision Note - Why this pricing structure fits the buyer and the value delivered: Basic fee covers API access, dashboard, integrations, support, and the first 500 verifications. Price per unit is charged after first 500 allowance. A hybrid pricing model works well because customers pay for access to a trusted verification platform and in proportion to the fraud prevention value they receive as their payment volume grows. The margins are 80.8%.

**Model:** hybrid

## Stress Tests

| Scenario | Impact on Margin | Response |
|----------|-----------------|----------|
| Inference costs 3x |-33.7% |Increase base fee by 10-20% |
| AI COGS per user 2x |-16.9% |Increase price per unit by $0.1 |
| Usage volume 4x |-50.5% |Increase both base fee and price per unit |

## Board One-Pager
<!-- Before/After: Old SaaS revenue vs. AI usage revenue for your product -->

**Before (traditional SaaS): Revenue: $1,000,000 
COGS: $700,000 
Gross Margin: 30% **
**After (AI-enabled): Revenue per customer (ARPU): ~$500/year
COGS per customer: $96/year
Gross profit per customer: $404/year
Gross margin: 80.8%
Customers needed for ~$2M ARR: ~4,000 **
**Net margin shift: Gross $ Change:
Original Gross Profit: $300,000
New Gross Profit: $1,616,000
Gross Profit Increase: +$1,316,000 (over 5× higher)
Margin Change:
Original Gross Margin: 30.0%
New Gross Margin: 80.8%
Increase: +50.8 percentage points
By moving from a labour-intensive verification business to an AI-powered verification platform, we dramatically improve our unit economics. Revenue doubles from $1M to $2M while COGS falls from $700k to $384k because AI automates the majority of verification work and scales at a much lower incremental cost than people. This increases gross margin from 30% to 80.8%, generating over $1.3M in additional gross profit. Beyond the financial improvement, the platform is more scalable, faster to serve customers, and creates a proprietary fraud intelligence dataset that becomes more valuable as transaction volume grows, strengthening our competitive advantage over time.
**
