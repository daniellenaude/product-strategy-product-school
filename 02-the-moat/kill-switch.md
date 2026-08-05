# Kill Switch Audit

## Vendor Dependency Assessment

| Dimension | Current State | Risk Level | 48-Hour Action |
|-----------|--------------|------------|---------------|
| **Provider** |Anthropic Claude is the only production LLM. All fraud reasoning and behavioral analysis depends on Claude API. | M |Review contracts to confirm usage and timeframe commitments, and begin negotiations if necessary| 
| **Abstraction** |Partial abstraction. There is a single LLM service wrapper, but prompts, output parsing, and Anthropic-specific features are embedded throughout the codebase. Swapping providers still requires changes in multiple services | L | Build a single LLMClient interface so all application code calls your interface instead of Anthropic directly.|
| **Routing** |None. Every request goes directly to Anthropic. No ability to route by model, customer tier, cost, or fallback provider. Provider is configured through environment variables only | M |Move provider selection into configuration. Add an environment variable so changing providers requires no code changes or redeployment |
| **Eval** | Mostly manual. Engineers occasionally compare prompt versions using historical fraud cases, but there is no automated benchmark, regression suite, or side-by-side provider comparison. Quality is judged by customer feedback and false positive/negative rates after deployment | M | Create a benchmark set of 50–100 historical verification cases. Run every provider against the same dataset and compare accuracy, latency, and cost to establish a baseline |

## Portability Score
<! Partial >

## If [primary vendor] doubles pricing tomorrow:
<!-- What's your 48-hour response? Within 48 hours, activate our secondary AI provider via the abstraction layer, benchmark it against our evaluation suite, and migrate production traffic to maintain service while renegotiating with the primary vendor -->

## If [primary vendor] ships a competing product:
<!-- What's defensible that they can't replicate? Our moat is proprietary bank verification outcomes and fraud intelligence built from real customer payment behavior, creating a continuously improving dataset that a model provider cannot replicate by releasing a generic AI feature -->
