# AI Engineering and Production Systems

How to design, evaluate, deploy, and operate AI systems that work reliably in production, not just in demos.

---

## What You Will Learn

- Evaluate AI platforms using a systematic four-pillar scorecard
- Understand the quality/latency/cost trade-off triangle and how to navigate it
- Design production-grade AI API integrations with proper error handling
- Build monitoring, observability, and alerting for AI systems
- Apply the four-tier deployment framework to match infrastructure to use case
- Assess AI platforms for enterprise security and compliance requirements

---

## The Gap Between Demo and Production

A recurring pattern in AI adoption: a team sees a compelling demo, builds a prototype that works beautifully in controlled conditions, then discovers that the production system behaves very differently.

Demo conditions:
- Hand-crafted prompts on curated inputs
- No concurrency, rate limits, or quotas
- No error handling for edge cases
- No monitoring or logging
- No cost visibility

Production conditions:
- Diverse, unpredictable real-world inputs
- Thousands of concurrent users
- Network failures, model timeouts, unexpected outputs
- Full observability requirements
- Cost that scales with usage

The discipline of **AI engineering** is the craft of closing this gap.

---

## Evaluating AI Platforms: The Four-Pillar Scorecard

When selecting an AI platform for organizational use, evaluate across four dimensions:

### Pillar 1: Performance

| Dimension | What to Measure |
|---|---|
| **Output quality** | Benchmark against your actual task types, not generic leaderboards |
| **Latency** | Time to first token; total response time; p95 and p99 latencies (not just average) |
| **Context window** | Maximum tokens supported; performance at long contexts (many models degrade) |
| **Reliability** | Historical uptime; SLA guarantees; behavior during outages |
| **Rate limits** | Tokens per minute; requests per minute; burst behavior |

---

### Pillar 2: Security

| Dimension | What to Assess |
|---|---|
| **Data handling** | Is your data used to train the model? How long is it retained? |
| **Transmission security** | TLS for all API traffic; certificate validation |
| **Access controls** | API key management; scoping; rotation policies |
| **Zero Data Retention (ZDR)** | Enterprise plans that process and discard immediately without logging |
| **Prompt injection mitigations** | What safeguards does the platform apply? |
| **Output filtering** | Content moderation capabilities; customization options |

---

### Pillar 3: Compliance

| Dimension | What to Assess |
|---|---|
| **SOC 2 Type II** | Has the provider completed a third-party security audit? |
| **GDPR/CCPA** | Data Processing Agreements available? Residency options? |
| **HIPAA** | BAA (Business Associate Agreement) available for healthcare data? |
| **FedRAMP** | Required for US government work |
| **Industry-specific** | PCI DSS for payments; SOX for public companies; FISMA for federal |

---

### Pillar 4: Administrative Controls

| Dimension | What to Assess |
|---|---|
| **User management** | Centralized admin console; role-based access; SSO integration |
| **Audit logging** | Who called which API, when, with what inputs? |
| **Usage monitoring** | Cost by team/project; quota alerts |
| **Policy enforcement** | Ability to restrict which models teams can access |
| **API key management** | Key rotation; scope limitation; expiration |

### The 5-Minute Enterprise Vetting Checklist

Before any pilot or purchase:
- [ ] SOC 2 Type II report available?
- [ ] Zero Data Retention option available for sensitive workloads?
- [ ] SSO integration (SAML/OIDC)?
- [ ] MFA enforced for all admin access?
- [ ] DPA (Data Processing Agreement) available?
- [ ] Audit log API available for compliance integration?

If any box is unchecked, assess whether the risk is acceptable or whether a different vendor is needed.

---

## The Quality / Latency / Cost Triangle

Every AI API call involves a fundamental trade-off. You can optimize for any two of three dimensions, but not all three simultaneously.

```
         Quality
           /\
          /  \
         /    \
        /      \
       /        \
      /          \
Latency ---------- Cost
```

**High quality + low latency** → high cost
(Use frontier models with minimal caching: GPT-4o, Claude Sonnet)

**High quality + low cost** → higher latency
(Use asynchronous processing, batch APIs, or accept slower responses)

**Low cost + low latency** → lower quality
(Use smaller, faster models: GPT-4o-mini, Claude Haiku, Llama 3 8B)

### Model Tiering Strategy

For most production applications, use multiple model tiers:

| Tier | Use Case | Examples |
|---|---|---|
| **Frontier** | Complex reasoning, nuanced judgment, critical decisions | GPT-4o, Claude Sonnet |
| **Mid-tier** | Standard tasks, most queries | GPT-4o-mini, Claude Haiku |
| **Local/Fast** | High-volume, low-complexity, latency-critical | Llama 3 8B (Ollama), Mistral 7B |

**Routing logic:**
```python
def select_model(task):
    if task.requires_complex_reasoning:
        return "claude-sonnet-4"
    elif task.is_standard and task.volume == "high":
        return "claude-haiku-4"
    else:
        return "claude-haiku-4"  # default to cost-efficient
```

---

## Production-Grade API Integration

### Rate Limiting and Retry Logic

Every production AI integration must handle rate limit errors gracefully.

```python
import anthropic
import time
from tenacity import retry, stop_after_attempt, wait_exponential

client = anthropic.Anthropic()

@retry(
    stop=stop_after_attempt(3),
    wait=wait_exponential(multiplier=1, min=4, max=60),
    reraise=True
)
def call_claude_with_retry(prompt: str, model: str = "claude-sonnet-4-6") -> str:
    try:
        message = client.messages.create(
            model=model,
            max_tokens=1024,
            messages=[{"role": "user", "content": prompt}]
        )
        return message.content[0].text
    except anthropic.RateLimitError as e:
        # Let tenacity retry
        raise
    except anthropic.APIError as e:
        # Log and handle permanent errors
        raise
```

**Key patterns:**
- **Exponential backoff**: Wait longer after each failure (4s, 8s, 16s...)
- **Jitter**: Add randomness to prevent thundering herd (all clients retrying simultaneously)
- **Circuit breaker**: Stop all requests when the API is clearly down; re-test after a delay

---

### Context Window Management

For applications that handle long conversations or large documents:

**Sliding window**: Keep only the most recent N tokens of conversation history
```python
def truncate_messages(messages, max_tokens=100000):
    # Always keep the system message
    # Keep as many recent messages as fit
    token_count = count_tokens(messages)
    while token_count > max_tokens and len(messages) > 1:
        messages.pop(1)  # Remove oldest non-system message
        token_count = count_tokens(messages)
    return messages
```

**Summarization strategy**: For very long conversations, periodically summarize the early history and replace it with a compact summary

**Chunking**: For document processing, split into overlapping chunks (e.g., 1000-token chunks with 200-token overlap) to ensure context at boundaries

---

### Structured Output

For applications that need to parse AI responses programmatically, always request structured output:

```python
# Request JSON output
prompt = """
Analyze this customer feedback and return a JSON object with:
{
  "sentiment": "positive|neutral|negative",
  "topics": ["array of topics mentioned"],
  "urgency": "low|medium|high",
  "summary": "one sentence summary"
}

Customer feedback: {feedback_text}

Return only valid JSON, no other text.
"""

# With Anthropic API (supports structured output natively in newer versions)
import json
response_text = call_claude_with_retry(prompt.format(feedback_text=feedback))
result = json.loads(response_text)
```

---

### Error Handling Taxonomy

| Error Type | HTTP Code | Meaning | Response |
|---|---|---|---|
| Authentication error | 401 | Invalid API key | Fix the key; alert the team |
| Rate limit | 429 | Too many requests | Retry with exponential backoff |
| Context too long | 400 | Input exceeds model limit | Chunk the input |
| Server error | 500/503 | Provider outage | Retry with backoff; fallback model |
| Timeout | — | Request exceeded deadline | Retry; increase timeout; reduce max_tokens |

---

## Observability: What to Monitor

You cannot improve what you cannot measure. Production AI systems require three layers of observability:

### Layer 1: Technical Metrics

| Metric | Why It Matters |
|---|---|
| **Latency** (p50, p95, p99) | p99 catches the worst user experiences |
| **Error rate** | Track rate limit errors, 500s, timeouts separately |
| **Token usage** | Input tokens, output tokens, by model and endpoint |
| **Cost per request** | Essential for unit economics |
| **Retry rate** | High retry rate → approaching rate limits |

---

### Layer 2: Quality Metrics

Technical health doesn't tell you if outputs are good. Track:

| Metric | How to Measure |
|---|---|
| **User feedback rate** | Thumbs up/down; explicit ratings |
| **Task completion rate** | Did the user achieve their goal? |
| **Hallucination rate** | Human evaluation of sample outputs |
| **Output consistency** | Same input → same output class? |
| **Prompt version performance** | A/B test different prompt versions |

---

### Layer 3: Business Metrics

Ultimately, what matters is business impact:

| Metric | Example |
|---|---|
| **Time saved per user** | Support ticket resolution time before vs. after AI |
| **Accuracy vs. human baseline** | AI classification accuracy vs. human annotator |
| **Cost per outcome** | Cost per successfully resolved ticket |
| **Escalation rate** | How often AI routes to human vs. handles directly |

---

### Alerting Strategy

Not every anomaly requires a wake-up call. Tier your alerts:

| Alert Level | Condition | Response |
|---|---|---|
| **Critical** | Error rate >5%; complete API outage | Immediate page; incident response |
| **High** | Error rate 2–5%; latency p99 >10s | Alert to on-call; investigate within 1 hour |
| **Medium** | Cost spike >50% of baseline; quality score drop | Alert to team; investigate within 4 hours |
| **Low** | Token usage trending up; new error type appearing | Daily digest; review in weekly meeting |

---

## The Four Deployment Tiers

Match your infrastructure to your actual scale and requirements:

| Tier | Use Case | Architecture | Who Manages |
|---|---|---|---|
| **Tier 1: Prototype** | Single user, development | API + application code, no optimization | Developer |
| **Tier 2: Team** | 10–100 users | API + caching + basic monitoring | Small engineering team |
| **Tier 3: Departmental** | 100–10,000 users | Load balancing + prompt caching + observability | Platform team |
| **Tier 4: Enterprise** | 10,000+ users | Multi-region + fallback models + full compliance stack | ML platform team |

Most internal tools operate at Tier 2 or 3. Consumer products often require Tier 4.

---

## Prompt Caching for Cost Optimization

Many AI APIs support prompt caching; when the same prompt prefix is sent repeatedly, the cached version is served at a significant discount.

**How it works:**
- Long static contexts (system prompts, document contexts) are cached server-side after the first call
- Subsequent calls that reuse the same prefix get a cache hit: typically 50–90% cost reduction on the cached portion
- Cache TTL: 5 minutes on Anthropic; varies by provider

**Design for caching:**
- Put static content (instructions, context, examples) at the beginning of your prompt
- Put dynamic content (the user's specific question) at the end
- Use the same static prefix across all requests in a session

---

## Hands-On Practice

### Exercise 1: Platform Audit

Choose one AI platform your organization currently uses or is evaluating. Complete the Four-Pillar Scorecard and the 5-Minute Enterprise Vetting Checklist. What gaps did you find? What would need to change before this platform could be used for sensitive production data?

---

### Exercise 2: Triangle Trade-Off Analysis

Think of a production AI use case you are working on or planning. For each of the three trade-off dimensions:
1. What is your requirement for quality?
2. What is your latency requirement?
3. What is your cost budget?

Based on this, which model tier is appropriate? Is a tiered approach (different models for different complexity levels) worth the added complexity?

---

### Exercise 3: Error Handling Implementation

Write a Python function that calls the Anthropic API with:
1. Retry logic (3 attempts, exponential backoff)
2. Logging of every call (model used, token count, latency, success/failure)
3. Graceful degradation: if Claude Sonnet fails after retries, fall back to Claude Haiku

---

### Exercise 4: Observability Design

For a hypothetical AI customer support agent:
1. List five technical metrics you would monitor
2. List three quality metrics you would track
3. List two business metrics that matter most
4. Define one Critical alert and one High alert with thresholds

---

## Summary

| Topic | Key Takeaway |
|---|---|
| **Platform evaluation** | Four pillars: Performance, Security, Compliance, Admin Controls; complete vetting checklist before procurement |
| **Trade-off triangle** | Quality, latency, and cost: choose two; use tiered models to serve different workloads appropriately |
| **Production integration** | Rate limiting, retry logic, context management, and structured output are non-negotiable for production |
| **Observability** | Monitor technical metrics + quality metrics + business metrics; tier alerts by severity |
| **Deployment tiers** | Match infrastructure to actual scale; don't over-engineer a prototype or under-engineer an enterprise system |
| **Prompt caching** | Design prompts with static content first; can cut API costs by 50–90% for repetitive workloads |

---

## Next Steps

- Continue to [Agent Orchestration](agent-orchestration.md) to learn how to coordinate multiple AI agents in production systems
- Complete the Platform Audit exercise for a real tool in your organization
- Implement error handling and logging in one existing AI integration this week
