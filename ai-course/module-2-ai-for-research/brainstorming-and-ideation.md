# Brainstorming and Ideation with AI

A structured approach to using AI as a creative partner: generating ideas at scale, pressure-testing them rigorously, and turning the best ones into concrete plans.

---

## What You Will Learn

- Use the Diverge → Deepen → Decide framework to structure AI-assisted ideation
- Apply the SCAMPER framework to systematically generate creative variations
- Pressure-test ideas with AI-powered adversarial analysis
- Select the best ideas using evaluation matrices
- Translate brainstorming output into structured proposals and documents

---

## The Problem with Traditional Brainstorming

Traditional brainstorming sessions suffer from two opposing failure modes:

1. **Too little divergence**: People self-censor, anchor to the first idea mentioned, or defer to authority, producing incremental thinking dressed up as innovation
2. **Too little convergence**: Sessions generate excitement but no actionable output; energy dissipates with nothing decided

AI changes both problems. It never self-censors, never runs out of ideas, and applies no social pressure. And with the right framework, AI can do the convergence work too, evaluating, ranking, and synthesizing ideas with structured criteria.

---

## The Three-Phase Framework: Diverge → Deepen → Decide

### Phase 1: Diverge (Maximize Quantity)

The goal of the Diverge phase is to generate as many ideas as possible without evaluating them. Judgment is explicitly suspended.

**The fundamental prompt structure:**
```
Generate [large number] different approaches to [problem/challenge].
Be creative and unconventional. Include ideas that seem impractical
or too simple. Do NOT evaluate or filter; just generate.
```

**Negative constraints unlock creativity:**
- *"Do NOT suggest the obvious solution of [common approach]."*
- *"Include at least 5 ideas that would be considered unusual or counterintuitive."*
- *"Generate ideas that span from free to enterprise-budget implementations."*

**Cross-domain thinking:**
> *"Generate 10 approaches to improving our customer onboarding, drawing inspiration from: amusement parks (wait time management), airlines (pre-flight checklists), or video game design (progressive difficulty)."*

Forcing the AI to apply analogies from unrelated domains is one of the most powerful ways to escape category thinking.

**Example diverge prompt:**
> *"We need to improve employee retention in a remote-first company. Generate 20 different ideas, ranging from low-cost culture initiatives to structural compensation changes. Include ideas that other companies have tried and ideas that no one has tried. Do NOT filter for feasibility."*

---

### Phase 2: Deepen (Pressure-Test the Best Ideas)

After the Diverge phase, you have raw material. Now select the 2–5 most promising ideas and rigorously analyze them.

**Pros and Cons analysis:**
> *"Take idea #3 (the mentorship rotation program) from the list above. Give me an honest analysis of its advantages, its risks, what it would cost to implement, and what could go wrong."*

**"What If" scenarios:**
> *"What if idea #7 worked better than expected? What second-order effects would that create? What if it failed? What would be the most likely cause?"*

**Adversarial pressure-testing:**
> *"Act as a skeptical CFO. Find the three most serious flaws in idea #12. What assumptions is it making that might not hold?"*

**Red-teaming:**
> *"You've been asked to make the case that idea #2 is a terrible idea. Build the strongest possible argument against it, even if you personally think it has merit."*

This is where AI's non-judgmental nature becomes a genuine asset. It will critique your favorite idea without feeling awkward about it.

---

### Phase 3: Decide (Select with Structured Criteria)

The Decide phase converts pressure-tested ideas into a clear recommendation. The key tool is an evaluation matrix, a grid that scores each idea against criteria that actually matter.

**Building an evaluation matrix prompt:**
> *"I have narrowed to three ideas: [A], [B], [C]. Score each one from 1–5 on these criteria: Expected impact on [metric], Implementation cost, Time to see results, Risk level, Alignment with our [stated value or constraint]. Create a table showing the scores and a total. Then recommend the winner and explain why."*

**Two common matrix types:**

| Matrix Type | Best For |
|---|---|
| **Usefulness vs. Novelty** | Creative decisions where differentiation matters (branding, product features) |
| **Impact vs. Effort** | Resource allocation decisions (prioritizing a roadmap) |

> *"Plot each of the five ideas on a 2×2 matrix. X-axis is Implementation Effort (low to high). Y-axis is Expected Impact (low to high). For each idea, assign a quadrant and explain your reasoning."*

---

## The SCAMPER Framework

SCAMPER is a structured checklist for generating creative variations of an existing idea, product, or process. It forces you to look at what you have from seven different angles.

| Letter | Operation | Prompt Template |
|---|---|---|
| **S** | Substitute | *"What if we replaced [component] with something else?"* |
| **C** | Combine | *"What if we merged this with [another thing]?"* |
| **A** | Adapt | *"What from another industry could we adapt to this problem?"* |
| **M** | Modify / Magnify | *"What if we made this 10x bigger, faster, or more frequent?"* |
| **P** | Put to another use | *"How else could this same thing be used?"* |
| **E** | Eliminate | *"What if we removed [element]? What's the simplest version?"* |
| **R** | Reverse / Rearrange | *"What if we did this in the opposite order?"* |

**Full SCAMPER prompt:**
> *"Apply the SCAMPER framework to our current [product/service/process]. For each of the seven operations, generate one or two concrete ideas. Be specific: not 'we could combine things' but 'we could combine our loyalty program with our referral program to create a single points-based system that rewards both behaviors.'"*

---

## From Ideas to Documents

Brainstorming output is raw material. To create value, it needs to become a structured proposal, pitch, or plan.

### The Structured Proposal Workflow

1. **Document your session output:**
   > *"Summarize this entire brainstorming conversation as a structured document: (1) The problem we were solving, (2) Ideas generated, (3) Ideas that were pressure-tested, (4) The recommended idea and its rationale."*

2. **Build the proposal structure first:**
   > *"Create an outline for a one-page proposal recommending idea #3. The audience is the leadership team. Include: executive summary, problem statement, proposed solution, implementation overview, expected outcomes, risks and mitigations."*

3. **Draft section by section:**
   > *"Draft the 'Problem Statement' section of this proposal. It should be 3–4 sentences, factual in tone, and establish why this is a priority now."*

4. **Refine for audience:**
   > *"The executive team cares primarily about cost savings and competitive positioning. Rewrite the 'Expected Outcomes' section to speak directly to those priorities."*

---

## Common Brainstorming Pitfalls

| Pitfall | What It Looks Like | Fix |
|---|---|---|
| **The Research Rabbit Hole** | Spending the session on background information instead of ideas | Separate research sessions from brainstorming sessions |
| **Evaluating Too Early** | Critiquing ideas during the Diverge phase | Suspend judgment explicitly; save critique for the Deepen phase |
| **Vague Ideas** | Ideas that sound good but can't be acted on | Add specificity: *"Make this 3x more concrete and actionable"* |
| **Single Perspective** | Running all analysis through one lens | Explicitly request multiple stakeholder perspectives |
| **Accepting the First Good Idea** | Stopping at the first satisfying option | Always generate at least 10–15 ideas before narrowing |

---

## Hands-On Practice

### Exercise 1: The Diverge Challenge

Choose a real problem you are working on. Set a timer for 10 minutes.

Use this prompt:
> *"Generate 20 completely different ideas for [your problem]. Vary them from simple and cheap to complex and expensive. Include unconventional ideas. Do not filter. Just list."*

After the output: identify the 3 ideas that surprised you most. Those are the ones most worth pressure-testing.

---

### Exercise 2: Cross-Domain Inspiration

Take a challenge in your work and apply cross-domain thinking:
> *"How might a [choose: hospital emergency room / Formula 1 racing team / luxury hotel / elementary school teacher] approach the problem of [your challenge]? Generate 5 specific ideas inspired by how that domain operates."*

Evaluate: what transferable insight emerged that you would never have generated from within your own domain?

---

### Exercise 3: Full SCAMPER Run

Take your current product, service, or process (something you know well). Run a full SCAMPER analysis:
> *"Apply SCAMPER to [your thing]. For each operation (Substitute, Combine, Adapt, Modify, Put to another use, Eliminate, Reverse), generate one specific, concrete idea. Explain what would change and why it might be valuable."*

Identify the top two SCAMPER ideas and run them through Phase 2 (Deepen) pressure-testing.

---

### Exercise 4: Decision Matrix

Take three ideas you've generated (from any exercise above). Create an evaluation matrix:
> *"Score these three ideas on a 1–5 scale for: expected impact, ease of implementation, cost, speed of results, and organizational fit. Present as a table with a total row. Recommend one and explain why."*

---

## Summary

| Topic | Key Takeaway |
|---|---|
| **Diverge** | Generate maximum quantity without judgment; use negative constraints and cross-domain prompts to escape category thinking |
| **Deepen** | Pressure-test the best 2–5 ideas with pros/cons, adversarial analysis, and "what if" scenarios |
| **Decide** | Use evaluation matrices (Impact vs. Effort, Usefulness vs. Novelty) to make structured, defensible recommendations |
| **SCAMPER** | A checklist for creative variation: Substitute, Combine, Adapt, Modify, Put to another use, Eliminate, Reverse |
| **Proposal workflow** | Summarize → Outline → Draft section by section → Refine for audience |

---

## Next Steps

- Continue to [Data Analysis with AI](data-analysis-with-ai.md) to apply structured thinking to quantitative research
- Apply the Diverge phase to your next real problem before the meeting where it will be discussed
- Save your best brainstorming prompts in a personal library for reuse
