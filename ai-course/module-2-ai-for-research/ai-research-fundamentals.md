# AI Research Fundamentals

How to use AI as a research partner: choosing the right tool, asking the right questions, and verifying what you get back.

---

## What You Will Learn

- Explain how AI research differs fundamentally from web search
- Choose the right AI research tool for different types of questions
- Apply six reusable research prompt patterns that work across any domain
- Implement a verification process to avoid acting on fabricated information
- Structure research findings into polished documents using AI assistance

---

## AI Research Is Not Search

When you type a query into Google, you are retrieving documents; the engine returns links to pages that contain the words you searched for. You then read those pages and synthesize the information yourself.

When you prompt an LLM for research, something fundamentally different happens. The model does not retrieve pages. It **synthesizes from its training data**, generating a response that integrates patterns across millions of documents it processed during training.

This distinction has profound implications:

| Dimension | Web Search | LLM Research |
|---|---|---|
| **What it does** | Retrieves existing documents | Synthesizes from training patterns |
| **Output** | Links to sources | A generated response |
| **Strength** | Current information, exact quotes | Conceptual synthesis, explanation, comparison |
| **Weakness** | Requires you to read and synthesize | No guarantee of accuracy; hallucination risk |
| **Best for** | Current events, specific facts, primary sources | Explanation, comparison, brainstorming, first-pass synthesis |

The best researchers use both: AI for the first-pass synthesis and conceptual understanding, and web search and primary sources for verification.

---

## Choosing the Right Research Tool

Not all AI research tools are equal. Before you start, match the tool to the question type.

| Tool | Information Access | Source Citation | Domain Strengths |
|---|---|---|---|
| **ChatGPT (GPT-4o)** | Training data + web browsing (Plus tier) | Sometimes provides links; not always reliable | General knowledge; coding; creative synthesis |
| **Claude** | Training data; no live web | Rarely cites; acknowledges uncertainty well | Long documents; careful reasoning; nuance |
| **Perplexity AI** | Live web search by default | Provides citations for all claims | Current events, factual questions needing verification |
| **Gemini** | Training data + live Google search | Provides web links | Google ecosystem; current information |
| **Elicit** | Academic papers (Semantic Scholar) | Cites specific papers with DOIs | Scientific research; literature review |
| **Consensus** | 200M+ academic papers | Summarizes evidence across studies | Scientific consensus on research questions |

> **Rule of thumb:** For conceptual questions where you want synthesis and explanation → any capable LLM. For factual questions where accuracy matters → Perplexity AI (cites sources) or Elicit/Consensus (academic). For current events → any tool with live web access.

---

## The Six Research Prompt Patterns

These reusable patterns work across virtually any domain. Learn them and you have a research toolkit that scales.

---

### Pattern 1: Expert Explanation

**When to use:** You need to understand a concept you are unfamiliar with.

**Template:**
```
Explain [concept] as if I am [audience level]. Cover:
- The core idea in plain language
- Why it matters / what problem it solves
- A concrete real-world example
- The most common misconception about it
```

**Example:**
> *"Explain retrieval-augmented generation as if I am a non-technical product manager. Cover the core idea in plain language, why it matters, a concrete real-world example, and the most common misconception about it."*

---

### Pattern 2: Analogy Request

**When to use:** A concept is abstract and you need it grounded.

**Template:**
```
Explain [complex concept] using an analogy from [familiar domain].
Make the analogy detailed enough to explain [specific aspect].
Then explain where the analogy breaks down.
```

**Example:**
> *"Explain how a neural network learns using an analogy from cooking. Make it detailed enough to explain the concept of 'training data.' Then explain where the analogy breaks down."*

---

### Pattern 3: Beginner's Guide

**When to use:** You want a structured overview of an unfamiliar field.

**Template:**
```
I am new to [field/topic]. Give me a beginner's guide that covers:
1. What it is and why it matters
2. The five most important concepts I need to understand first
3. The most common beginner mistakes
4. The best next step for someone starting from scratch
```

---

### Pattern 4: Multi-Source Synthesis

**When to use:** You want to understand the range of perspectives on a topic.

**Template:**
```
Summarize the main perspectives on [topic]. For each perspective:
- State the core argument
- Identify who tends to hold it and why
- Name its strongest evidence
- Name its main weakness or criticism

Then identify where most serious experts agree, and where the genuine debate lies.
```

---

### Pattern 5: Contradiction Analysis

**When to use:** You've heard conflicting claims and want to understand why.

**Template:**
```
I've heard two conflicting claims about [topic]:
Claim A: [first claim]
Claim B: [second claim]

Explain:
1. The context in which each claim is true or reasonable
2. Whether these are genuinely contradictory or addressing different questions
3. What the current best evidence suggests
4. What remains genuinely uncertain
```

---

### Pattern 6: Sourcing Mandate

**When to use:** You need verifiable claims, not synthesis.

**Template:**
```
Provide an overview of [topic]. For each major claim you make:
- Indicate whether you are drawing from well-established consensus or more specific sources
- Flag any claims that are contested or uncertain
- Tell me which claims I should verify independently before acting on them
```

> **Warning:** Even with the Sourcing Mandate pattern, LLMs can fabricate citations. If an AI names a specific study or paper, verify that it actually exists before including it in your work. Use Perplexity AI or Google Scholar to check.

---

## The Verification Process

Using AI research without verification is like buying a used car without a test drive. Here is the three-step process:

**Step 1: Demand transparency**
Ask the AI to flag uncertain claims and tell you which assertions need verification. The Sourcing Mandate pattern (above) builds this in by default.

**Step 2: Verify existence**
If the AI cites a specific source (study, book, article, statistic), verify it exists before using it. Copy the title or citation into Google Scholar, Google, or the publisher's website.

**Step 3: Verify content**
Even if the source exists, verify that it actually says what the AI claimed. Summaries can be wrong. Read the abstract or relevant section yourself.

> **Real-world case:** A lawyer submitted a brief containing six AI-generated case citations. When opposing counsel reviewed them, several of the cases were entirely fabricated by the AI. The resulting sanctions and professional embarrassment were entirely preventable with a 10-minute verification step.

### The Verification Pyramid

| Level | Rigor | When to use |
|---|---|---|
| **Level 1: Gut Check** | Low | Does this seem plausible based on my expertise? |
| **Level 2: Secondary Source** | Medium | Find one independent source that confirms the claim |
| **Level 3: Primary Source** | High | Read the original study, document, or data yourself |

Use Level 1 for internal brainstorming. Use Level 2 for external communications. Use Level 3 for anything published, legal, or consequential.

---

## Structuring Research into Documents

The output of research is rarely a conversation; it is a document, report, or presentation. AI accelerates this final step too.

### The Outline-First Method

Never ask AI to write a document from scratch. Build the structure first, then fill it.

1. **Research phase**: Use the patterns above to gather and understand your material
2. **Outline phase**: Ask AI to help organize your notes into a logical structure
   > *"Here are my research notes on [topic]. Organize them into a logical outline for a [document type] aimed at [audience]. The outline should have 4-6 major sections."*
3. **Draft phase**: Expand section by section
   > *"Draft Section 2 of the outline in detail. Aim for approximately 300 words. Use the research notes I provided."*
4. **Transitions**: Ask AI to write bridging sentences between sections
5. **Refinement passes**: Three targeted refinements work better than one vague "make it better"
   - Pass 1: *"Make this more concise. Cut any sentence that doesn't add new information."*
   - Pass 2: *"Adjust the tone for [audience]. They care about [their priorities]."*
   - Pass 3: *"Add a clear call to action and summary in the final section."*

### The Master Briefing Document

For complex, multi-session research projects, maintain a Master Briefing Document, a single file that accumulates your research context and can be pasted into new AI sessions to restore context.

Structure it as:
```
PROJECT: [Name and goal]
AUDIENCE: [Who will read the final output]
KEY FINDINGS SO FAR: [Bullet points]
OPEN QUESTIONS: [What still needs answering]
CONSTRAINTS: [Length, tone, format requirements]
```

Paste this at the top of each new research session to avoid re-explaining everything.

---

## Hands-On Practice

### Exercise 1: Pattern Comparison

Choose a topic relevant to your work. Use the same topic with:
1. The Expert Explanation pattern
2. The Analogy Request pattern
3. The Multi-Source Synthesis pattern

Compare the three outputs. Which gave you the most useful understanding? Which would you use in different situations?

---

### Exercise 2: Verification in Action

Ask an LLM:
> *"What does the research say about the effectiveness of [a practice relevant to your field]? Name at least two specific studies."*

Take each named study and attempt to verify it on Google Scholar or PubMed. Document your findings: how many were real, partially real (the study exists but doesn't say what was claimed), or fabricated?

---

### Exercise 3: Research-to-Document Workflow

Pick a topic you need to understand better for your work. Run a full research workflow:
1. Use the Expert Explanation pattern to get a foundation
2. Use the Contradiction Analysis pattern to understand debates in the field
3. Use the Sourcing Mandate pattern to identify what needs verification
4. Verify three key claims
5. Ask AI to organize your findings into a four-section outline

Reflect: How long did this take compared to traditional research? What human judgment was essential?

---

## Summary

| Topic | Key Takeaway |
|---|---|
| **AI vs. web search** | AI synthesizes from training patterns; web search retrieves documents. Both are needed. |
| **Tool selection** | Match the tool to the question: Perplexity for current facts, Elicit/Consensus for academic, ChatGPT/Claude for synthesis |
| **Six patterns** | Expert Explanation, Analogy, Beginner's Guide, Multi-Source Synthesis, Contradiction Analysis, Sourcing Mandate |
| **Verification** | Always verify specific claims; the three-step process (demand transparency, verify existence, verify content) is non-negotiable |
| **Outlining** | Build structure first, then fill section by section; never ask AI to write a complete document from scratch |

---

## Next Steps

- Continue to [Prompt Engineering: Beginner to Advanced](prompt-engineering.md) to master the single most important skill for getting value from AI
- Start a Master Briefing Document for your next research project
- Try the Sourcing Mandate pattern on your next AI research task and apply the verification process
