# AI Writing and Text Generation

How to use AI to produce professional written content: with a consistent brand voice, across formats, at scale.

Writing is one of the most immediately practical applications of AI for research and knowledge work. Whether you are summarizing findings, drafting reports, preparing communications, or repurposing content across channels, AI writing tools let you produce more in less time without sacrificing quality. This guide gives you a repeatable system for getting professional results.

---

## What You Will Learn

- Establish and teach your brand voice to AI tools
- Apply the three-part framework for professional text generation
- Use iterative refinement to move from draft to polished output
- Generate emails, reports, social media posts, and long-form documents efficiently
- Adapt content for different audiences and channels from a single source

---

## Why Brand Voice Matters More Than AI Skill

Here is the most common mistake people make with AI writing: they ask the tool to "write in a professional tone" or "make it sound natural," and then wonder why every output sounds the same. Generic. Like a corporate press release. Written by no one in particular, for no one in particular.

The breakthrough comes when you stop asking AI to guess at your voice and start showing it what your voice actually is.

> **The rule:** AI defaults to the statistical average of all the writing it was trained on. That average is competent, bland, and indistinguishable from a thousand other brands. Your job is to pull the output away from that average and toward something specific.

---

## Step 1: Find and Define Your Voice

Your voice is not your logo or your color palette. It is the specific way you use language: the rhythm of your sentences, the words you choose, the things you say and don't say.

To teach your voice to an AI, collect 3 to 5 pieces of writing that already sound like you at your best. These could be:
- An email you wrote that got a great response
- A section of a document you were proud of
- A presentation script that landed well
- A social post that generated strong engagement

Then analyze them with AI:
> *"Read these writing samples I've provided. Identify my brand voice: the tone, style, sentence structure, vocabulary choices, and any patterns you notice. Summarize it as a 'voice guide' with 5 to 7 specific characteristics."*

**Example voice guide output:**
- **Tone**: Direct and confident, but never arrogant
- **Sentence structure**: Short declarative sentences; rarely more than 20 words
- **Vocabulary**: Plain English; no jargon unless the audience expects it
- **Personality**: Occasionally uses a rhetorical question to create engagement
- **What we don't do**: No exclamation marks; no corporate clichés ("synergy," "leverage," "circle back")

Now paste this voice guide at the top of your prompts. The AI will use it as a style constraint.

---

## The Three-Part Text Generation Framework

Structure your prompts in three parts:

**Setup** (Who you are and who you're writing for)
```
Act as a [role] writing for [audience].
Voice guide: [paste your voice characteristics]
Context: [relevant background the AI needs]
```

**Task** (What specifically to write)
```
Write a [format] that [accomplishes this goal].
[Any specific points to include]
[Any points to exclude or avoid]
```

**Execution** (Format and constraints)
```
Format: [specific structure or format]
Length: [word count or constraint]
Deadline/urgency signal: [if relevant]
```

---

## Common Writing Formats and Their Prompts

### Professional Email

```
Act as a [your role] at [company type]. Voice guide: [paste].

Write an email to [recipient and their role] about [topic].

Key points to cover:
- [Point 1]
- [Point 2]
- [Point 3]

End with a clear call to action: [what you want them to do].
Tone: [professional/warm/urgent]. Length: under 200 words.
```

---

### Executive Summary

```
Act as a senior analyst. Write an executive summary of the following
[report/meeting/analysis].

The audience is [audience] who care most about [their priorities].
Lead with the most important finding and its business implication.
Then cover: [Key Finding 1], [Key Finding 2], [Recommendation].
Format: 3 to 4 short paragraphs. No bullet points. Under 250 words.

[Paste source material]
```

---

### Blog Post and Long-Form Article

Step 1: Structure first
```
I am writing a [length] article about [topic] for [audience].
Generate an outline with: a compelling hook, 4 to 5 main sections with
subheadings, and a conclusion with a clear call to action.
```

Step 2: Draft section by section
```
Using the outline above, draft the [section name] section.
Approximately [word count] words. Voice guide: [paste].
Include: [specific points]. Start with [specific type of opening].
```

Step 3: Connect the sections
```
Write a two-sentence transition between [Section A] and [Section B]
that explains the logical progression.
```

---

### Social Media

**LinkedIn post:**
```
Write a LinkedIn post announcing [topic]. Audience: [audience].
Start with a hook that creates curiosity or shares a concrete insight
(not "I am pleased to announce").
Voice: [characteristics]. Length: 150 to 200 words. No hashtag stuffing.
End with a question to generate comments.
```

**Twitter/X thread:**
```
Turn this [article/idea] into a Twitter thread of 7 tweets.
Tweet 1: A bold hook that makes people want to read the rest.
Tweets 2 to 6: One key insight per tweet, under 280 characters each.
Tweet 7: A clear takeaway and call to action.
Keep it conversational, not corporate.
```

---

### Meeting and Presentation Script

```
Act as a communications coach. Write a 3-minute spoken script
for [audience and occasion].

The core message I need to land: [one sentence].
Supporting points: [2 to 3 bullet points].
Tone: [conversational/authoritative/inspiring].
Note: This will be spoken aloud. Use natural language, not written prose.
Include a strong opening line and a memorable closing.
```

---

## The Iterative Refinement Cycle

Never expect a first draft to be final. Plan for at least two or three refinement passes, each targeting something specific.

```
Draft 1 -> Structural pass -> Draft 2 -> Voice pass -> Draft 3 -> Audience pass -> Final
```

**Structural pass:**
> *"Read this draft. Identify any section that doesn't add new information or doesn't serve the stated goal. Recommend what to cut."*

**Voice pass:**
> *"Compare this draft to the voice guide: [paste]. Where does the draft drift from the established voice? Rewrite the sections that sound off-brand."*

**Audience pass:**
> *"This draft is for [audience]. They care about [their priorities]. Where does the draft speak to irrelevant concerns or miss what they actually care about? Revise the framing."*

**Length pass:**
> *"This draft is [X] words. Cut it to [Y] words without losing the three core ideas: [list them]."*

---

## Content Repurposing: One Source, Many Formats

One of the highest-leverage uses of AI writing assistance is converting a single source into multiple formats simultaneously.

**Repurposing prompt:**
```
Here is a [source document/article/report]: [paste]

Create each of the following from this source:
1. A 250-word summary suitable for an email newsletter
2. A 3-tweet Twitter thread hitting the three most important points
3. A 150-word LinkedIn post with a hook, key insight, and question
4. Five key takeaways as bullet points for an internal Slack post
5. A one-paragraph description for a website "Resources" page
```

**When to repurpose:**
- After a major company announcement
- After publishing a new research piece or report
- After a key conference presentation or webinar
- After any event that generates content worth amplifying

---

## Hands-On Practice

### Exercise 1: Voice Analysis

Collect three pieces of your best writing (or your organization's best writing). Paste them into an LLM and ask for a voice guide. Evaluate the output: does it accurately capture your style? What did it miss? Refine until it does.

---

### Exercise 2: The Three-Format Challenge

Take one piece of information (a project update, a product announcement, a data finding). Generate three formats from it:
1. A professional email to a stakeholder
2. A LinkedIn post for your professional network
3. A bullet-point summary for an internal team

Evaluate: what had to change in each format? Which required the most editing?

---

### Exercise 3: The Refinement Cycle

Write one piece of content (any format) using a single initial prompt. Then run three targeted refinement passes:
1. Structural: cut anything that doesn't serve the goal
2. Voice: align with your brand voice guide
3. Audience: adjust for your specific reader

Compare the initial draft to the final version. What changed? How many refinement passes would have been enough?

---

### Exercise 4: Repurposing Sprint

Find a long-form piece of content your organization has produced (a report, a blog post, a case study). In one session, use AI to repurpose it into four formats:
- Executive summary email
- LinkedIn post
- Twitter thread
- Internal Slack post

How long did this take? What would it have taken manually?

---

## Summary

| Topic | Key Takeaway |
|---|---|
| **Brand voice** | Define it explicitly using real examples; paste it into prompts as a style constraint |
| **Three-part framework** | Setup (who you are and context) then Task (what to write) then Execution (format and constraints) |
| **Common formats** | Email, executive summary, blog post, social media, script: each has a specific prompt structure |
| **Iterative refinement** | Structural, voice, audience, and length passes are more effective than "make it better" |
| **Repurposing** | One source into many formats is one of the highest-leverage uses of AI writing assistance |

---

> **Next steps:** Continue to [Module 3: AI for Content Creation](../module-3-ai-content-creation/) to learn how to generate professional images, audio, and video with AI tools.
