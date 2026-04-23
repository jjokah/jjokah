# Data Analysis with AI

How to use AI as an analytical partner: turning raw data into structured insights, clear narratives, and stakeholder-ready reports.

---

## What You Will Learn

- Apply the Four-Step EDA methodology (Orient, Visualize, Correlate, Hypothesize) with AI assistance
- Generate business insights using the Win/Challenge/Opportunity framework
- Adapt data narratives for different stakeholder audiences
- Validate AI-generated insights for accuracy and bias
- Draft complete data reports using an outline-first approach

---

## From Data to Story

Every organization has more data than it can use. The bottleneck is not collection; it is interpretation. What does this data mean? What decisions should it inform? What should we do next?

This is where AI fundamentally changes what is possible. An analyst who once spent 80% of their time on data wrangling and 20% on interpretation can now invert that ratio. AI handles the mechanical processing; the human focuses on the judgment-intensive work: framing the right questions, validating the answers, and communicating the story.

> **Example:** A customer success team receives 2,400 support tickets per month. Manually categorizing and analyzing them would take a dedicated analyst days. With AI, you can paste a representative sample, ask for thematic categorization and frequency analysis, and have a structured breakdown in minutes, with the analyst's time spent on validation and strategic response, not counting.

---

## AI Data Tools: Know Your Options

| Tool | Best For | Key Capability |
|---|---|---|
| **ChatGPT (Code Interpreter / Data Analysis)** | Uploading CSV/Excel files for direct analysis | Runs Python, creates charts, answers natural language questions about the data |
| **Claude** | Long-form data summaries, qualitative analysis, text-heavy datasets | Handles large amounts of pasted text; excellent at thematic analysis |
| **Julius AI** | Interactive data analysis without code | Conversational interface for spreadsheets and databases |
| **Gemini Advanced** | Google Sheets integration | Analyze data in-place within Google Workspace |
| **Tableau AI / Power BI Copilot** | Business intelligence visualization | Natural language querying of structured BI dashboards |

> **Tip:** For quantitative data in spreadsheets, ChatGPT's Code Interpreter or Julius AI allow you to upload files and query them directly. For qualitative data (text, feedback, survey responses), pasting into Claude or ChatGPT and asking for thematic analysis is often faster and more effective.

---

## The Four-Step EDA Methodology

**Exploratory Data Analysis (EDA)** is a systematic approach to understanding a new dataset. AI accelerates all four steps.

### Step 1: Orient (Get the Lay of the Land)

Before asking for insights, establish a shared understanding of what the data contains.

**Prompt template:**
```
Here is a sample of data about [topic]. [Paste data]

Please orient me to this dataset:
1. What are the main categories or dimensions present?
2. What is the range of values or responses?
3. What patterns are immediately visible?
4. What seems most significant or unusual?
```

**Example with support ticket data:**
> *"Here are 50 support tickets from last month. Orient me to this dataset: what themes are recurring, what types of issues appear most frequently, and what stands out as unusual?"*

---

### Step 2: Visualize (See the Patterns)

Ask AI to suggest or create appropriate visualizations, or to describe what a visualization would show.

**For chart suggestions:**
> *"Based on this dataset about [topic], what visualization types would best show the distribution across [variable]? For each suggestion, explain what the chart would reveal and when it's most appropriate."*

**For categorical breakdowns:**
> *"Categorize these 200 customer responses into themes. For each theme, provide: the theme name, a one-sentence description, representative examples, and the approximate count or percentage."*

**Choosing chart types:**

| Data type | Best visualization |
|---|---|
| Part-to-whole proportions | Pie chart, stacked bar |
| Comparisons across categories | Bar chart, lollipop chart |
| Trends over time | Line chart |
| Distribution of values | Histogram, box plot |
| Relationship between two variables | Scatter plot |
| Geographic data | Map |

---

### Step 3: Correlate (Find Hidden Relationships)

The most valuable insights often come not from what the data shows in isolation, but from what happens when you cross-reference datasets or segments.

**Correlation prompts:**
> *"In this dataset, does [variable A] correlate with [variable B]? What pattern do you see when you look at [segment] versus [other segment]?"*

> *"Here are satisfaction scores (Dataset A) and response time data (Dataset B). What relationship do you see between response time and satisfaction score? Is it consistent across different customer tiers?"*

**Segment comparison:**
> *"Compare the feedback themes for customers in the Enterprise tier versus the Startup tier. What concerns are unique to each segment? What do they have in common?"*

---

### Step 4: Hypothesize (Generate Testable Explanations)

Once patterns are visible, ask AI to help formulate testable business hypotheses.

**Hypothesis generation prompts:**
> *"We see that customer churn is higher among users who never completed our onboarding checklist. Generate three testable hypotheses that could explain this relationship. For each hypothesis: state it clearly, describe how we would test it, and identify what data we would need."*

> *"The data shows a spike in support tickets every Monday morning. Generate four possible explanations and describe what additional data would confirm or rule out each one."*

**Good hypotheses are:**
- Specific and falsifiable (capable of being proven wrong)
- Tied to an action you could actually take
- Grounded in the data rather than pre-existing assumptions

> **Warning:** Watch for the correlation/causation trap. AI will faithfully identify correlations in your data. It is your job as the analyst to assess whether a causal relationship is plausible, and what additional evidence would be needed to establish it.

---

## Generating Insights: The Win/Challenge/Opportunity Framework

Once the four steps are complete, structure your findings using the Win/Challenge/Opportunity framework. This converts raw analytical output into strategic business language.

**Prompt:**
```
Based on the analysis above, structure the key findings using this framework:

WINS: What is working well and should be protected or scaled?
CHALLENGES: What is not working and needs immediate attention?
OPPORTUNITIES: What trends or gaps suggest potential for improvement?

For each item: state the finding, quantify it where possible, and
suggest one specific action it implies.
```

**Example output structure:**

| Category | Finding | Implication |
|---|---|---|
| **Win** | 94% of tickets resolved within 4 hours for Enterprise customers | Maintain current SLA; use as case study for upsell |
| **Challenge** | 38% of all tickets relate to the same onboarding step | Redesign step or create proactive in-app guidance |
| **Opportunity** | Startup tier customers who complete onboarding have 60% lower churn | Build automated onboarding completion nudges for this segment |

---

## Stakeholder Adaptation

The same data tells different stories to different audiences. AI makes it fast to create multiple versions.

**The base prompt:**
> *"I have the following analysis: [paste summary]. Now rewrite the key findings and recommendations for three different audiences:"*
> 1. *"A non-technical executive (CEO/CFO) who cares about business impact, cost, and competitive position"*
> 2. *"A product team that will implement the changes"*
> 3. *"A customer success team that will communicate the changes to clients"*

**What changes for each audience:**
- **Executives**: Lead with business impact and numbers; minimize process detail
- **Product teams**: Lead with user behavior patterns and specific friction points; include implementation context
- **Customer-facing teams**: Lead with customer sentiment; provide talking points for conversations

---

## Validating AI-Generated Insights

AI can be confidently wrong. Before presenting data analysis to stakeholders, validate:

**Source verification:**
- If AI generated a specific statistic, trace it back to the original data
- AI can confuse which data point came from which source when multiple datasets are involved

**Bias checks:**
- **Aggregation bias**: Does the average hide important variation? (E.g., average satisfaction score masks 10% of customers who gave 1-star reviews)
- **Selection bias**: Is the data you analyzed representative of all customers, or just the ones who responded?
- **Recency bias**: Is AI over-weighting the most recent data in your sample?

**The gut check:**
- Does this finding align with what your team has been seeing anecdotally?
- If a finding is surprising, does the data actually support it, or is it an artifact of how you framed the question?
- What would a reasonable skeptic say about this conclusion?

**Contextual plausibility:**
> *"Does this finding make sense given what we know about our business and customers? Flag any conclusion that seems implausible or that contradicts what we expected."*

---

## Drafting the Report

The final product of data analysis is usually a document: a report, a presentation, or an executive brief.

**Step 1: Request a structured outline**
> *"Create an outline for a data analysis report on [topic] for [audience]. Include: Executive Summary, Key Findings (3–4), Supporting Analysis, Recommendations, and Next Steps."*

**Step 2: Draft section by section**
> *"Draft the Executive Summary section. It should be 150 words or less. Lead with the single most important finding and the action it implies."*

**Step 3: Generate transitions**
> *"Write a two-sentence transition between the 'Key Findings' and 'Recommendations' sections that explains how the findings lead to the recommendations."*

**Step 4: Narrative refinement**
> *"The current draft reads as a list of data points. Rewrite it to read as a coherent narrative, one finding leading logically to the next, building toward the recommendation."*

---

## Hands-On Practice

### Exercise 1: The Four-Step Analysis

Find a dataset you have access to, even a simple spreadsheet from your work. Run it through all four steps:
1. **Orient**: Ask AI to describe what's in the data
2. **Visualize**: Ask AI to suggest three chart types appropriate for the data and explain what each would show
3. **Correlate**: Ask AI to identify the most interesting relationship between two variables
4. **Hypothesize**: Ask AI to generate two testable explanations for the most surprising pattern

---

### Exercise 2: The Win/Challenge/Opportunity Framework

Take any dataset or summary of results from your work (even meeting notes or a survey summary). Apply the WCO framework prompt above. Evaluate:
- How complete is the output?
- What did AI miss that your domain knowledge catches?
- Which finding would most change what your team does next week?

---

### Exercise 3: Stakeholder Adaptation

Take one analytical finding you have. Use AI to rewrite it for three audiences: your manager, your customers, and your technical team. Compare the three versions.

What had to change most dramatically? What stayed the same? How does this change how you think about presenting data?

---

### Exercise 4: Bias Hunt

Take an AI-generated insight from any exercise above. Deliberately try to find the flaw:
- What data is missing from this analysis?
- What segment or population is excluded?
- What alternative explanation does the data not rule out?
- What would change if the sample size were 10x larger?

---

## Summary

| Topic | Key Takeaway |
|---|---|
| **Four-Step EDA** | Orient → Visualize → Correlate → Hypothesize; AI accelerates all four steps but human judgment drives each |
| **Win/Challenge/Opportunity** | Structures raw findings into strategic business language with clear implications |
| **Stakeholder adaptation** | The same analysis tells different stories to different audiences; AI makes multiple versions fast |
| **Validation** | Source verification, bias checks, and the gut check are non-negotiable before presenting findings |
| **Report drafting** | Outline first → draft section by section → add transitions → refine narrative |

---

## Next Steps

- Continue to [Evaluating and Debugging AI Outputs](evaluating-ai-outputs.md) to build the critical evaluation habit that protects every analysis
- Try running a real dataset through the Four-Step methodology this week
- Use the WCO framework on the next data summary you share with your team
