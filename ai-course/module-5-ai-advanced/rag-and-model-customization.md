# RAG and Model Customization

How to adapt AI models to your specific domain: using Retrieval-Augmented Generation, fine-tuning, and local deployment to move beyond generic AI capabilities.

---

## What You Will Learn

- Understand why pre-trained models need customization for production use cases
- Design a Retrieval-Augmented Generation (RAG) pipeline from scratch
- Choose between RAG, fine-tuning, and prompt engineering using a structured decision framework
- Apply parameter-efficient fine-tuning techniques (LoRA, QLoRA)
- Evaluate the hidden costs of custom AI systems
- Set up local LLM deployment using Ollama

---

## Why Generic Models Need Customization

Out-of-the-box frontier models are generalists, trained on the breadth of human knowledge, optimized for general helpfulness. This makes them useful for most tasks. But for production applications, "generally capable" is rarely enough.

**The three core limitations of vanilla LLMs:**

**1. Knowledge cut-offs**
All models have a training cut-off date. They have no knowledge of events, products, regulations, or data that appeared after that date. A model trained with a January 2024 cut-off knows nothing about your Q3 2024 earnings, your new product launched in September, or a regulatory change from last month.

**2. Private data blindness**
The model was not trained on your internal documentation, your customer data, your policies, your codebase. It cannot access or reason about information it was never trained on.

**3. Hallucination in narrow domains**
When asked about a highly specific domain where training data was sparse (your proprietary system's API, a niche industry regulation, your organization's internal processes) models are more likely to hallucinate plausible-sounding but incorrect information.

The customization techniques in this guide address these three limitations.

---

## Pre-Trained Models: The Foundation

All customization starts from a pre-trained model. Rather than training from scratch (billions of dollars and months of compute), you start with an existing model and adapt it.

### Where to Find Models

| Source | What's Available | Best For |
|---|---|---|
| **Hugging Face** | Thousands of open-source models across all tasks | Research, fine-tuning, local deployment |
| **OpenAI API** | GPT-4o, GPT-4o-mini, embeddings | Production applications needing frontier quality |
| **Anthropic API** | Claude 3.5 Sonnet, Claude Haiku, Opus | Complex reasoning, long context, careful outputs |
| **Google Vertex AI** | Gemini models, PaLM 2 | Google ecosystem; multimodal; enterprise |
| **AWS Bedrock** | Multi-provider (Anthropic, Meta, Mistral) | Enterprise; unified access; compliance |

### Model Evaluation Criteria

Before selecting a model:

| Criterion | What to Assess |
|---|---|
| **Task performance** | Benchmark scores for your specific task type |
| **Context window** | Does it fit your documents? |
| **Licensing** | MIT and Apache 2.0 allow commercial use; some models restrict it |
| **Latency** | Time to first token for your use case |
| **Cost** | Price per million tokens for expected volume |
| **Privacy** | Does the API provider retain your data? |

---

## Retrieval-Augmented Generation (RAG)

RAG is the most commonly deployed technique for grounding AI responses in specific, current, private information, without the cost and complexity of fine-tuning.

### The Problem RAG Solves

Imagine a customer support AI that needs to answer questions about your specific products, policies, and procedures. You can't train a new model for every policy update. And you can't fit your entire knowledge base into every prompt; the context window isn't large enough and the cost would be prohibitive.

RAG solves this by separating knowledge storage from the model's reasoning:
- The model handles language understanding and reasoning
- A knowledge base handles information storage
- Retrieval connects them at query time

### The Three-Step RAG Process

```
User Query → Retrieve → Augment → Generate
```

**1. Retrieve**: Convert the user's query to an embedding; search the knowledge base for the most semantically similar chunks; return the top N results.

**2. Augment**: Inject the retrieved chunks into the model's prompt as context.

**3. Generate**: The model answers the question using the retrieved information, not just its training data.

### RAG Architecture

**The Retriever:**
- **Vector database**: Stores embeddings of all your documents (Pinecone, Weaviate, Chroma, pgvector)
- **Embedding model**: Converts both documents and queries to vectors (OpenAI text-embedding-3, Cohere Embed)
- **Search algorithm**: Finds vectors most similar to the query vector

**The Generator:**
- Any capable LLM (GPT-4o, Claude, Llama 3)
- Receives the query + retrieved chunks as context
- Generates an answer grounded in the retrieved material

### Document Preparation

Before documents can be retrieved, they must be chunked, divided into segments that:
- Fit within the context window of your retrieval model
- Are semantically coherent (not splitting a paragraph in the middle of a sentence)
- Are small enough to be specific, large enough to carry complete ideas

**Chunk sizes:**
- 256–512 tokens: high precision retrieval; may miss context
- 512–1024 tokens: best balance for most use cases
- 1024–2048 tokens: more context per chunk; may reduce precision

**Chunking strategies:**
- **Fixed size**: Split every N tokens (simple but may break sentences)
- **Sentence-based**: Split on sentence boundaries (more natural)
- **Semantic chunking**: Use an LLM to identify logical breakpoints (highest quality; highest cost)

### RAG Failure Modes

| Failure | Cause | Fix |
|---|---|---|
| **Vocabulary mismatch** | Query uses different terminology than documents | Expand queries with synonyms; use a more powerful embedding model |
| **Knowledge base drift** | Documents updated but embeddings not refreshed | Build an update pipeline; monitor staleness |
| **Context overload** | Too many chunks retrieved; model confused | Reduce top-K; add re-ranking step |
| **Missing information** | Question requires knowledge not in the knowledge base | Acknowledge gaps rather than hallucinate |

### Advanced RAG Patterns

**Hybrid Retrieval**: Combine semantic search (embeddings) with keyword search (BM25). Semantic search handles meaning; keyword search handles exact matches. Union the results for better coverage.

**Query Expansion**: Before searching, use an LLM to rephrase the query multiple ways. Search with all versions and combine results. Addresses vocabulary mismatch.

**Re-ranking**: After initial retrieval, use a cross-encoder model to re-score the chunks by relevance. More expensive but significantly improves precision.

---

## Model Fine-Tuning

Fine-tuning adapts a pre-trained model by training it further on a domain-specific dataset. Unlike RAG, fine-tuning changes the model's weights; it learns the adaptation, rather than retrieving it.

### When Fine-Tuning Is the Right Choice

Fine-tuning excels when:
- You need consistent **style, tone, or format** across all outputs (RAG doesn't help with this)
- You need to teach **domain-specific vocabulary** or specialized reasoning patterns
- **Low latency matters**: Fine-tuned models don't need a retrieval step
- Your use case involves **classification, extraction, or structured output** from known patterns

Fine-tuning is NOT the right choice when:
- You need access to **current or frequently updated information** (use RAG)
- Your dataset is **too small** (under a few hundred high-quality examples; most fine-tuning needs thousands)
- You need to **remove knowledge** from a model (fine-tuning cannot reliably do this)
- Budget is limited (fine-tuning requires a significant data preparation investment)

### Types of Fine-Tuning

**Supervised Fine-Tuning (SFT)**: Train on input-output pairs in your domain.
Example: Hundreds of (customer query → ideal support response) pairs.

**Alignment Fine-Tuning (RLHF)**: Use human feedback to train the model toward preferred behaviors. Used by OpenAI and Anthropic on their frontier models. Rarely done by individual organizations; requires significant ML expertise.

**Parameter-Efficient Fine-Tuning (PEFT)**: Adapt a small subset of the model's weights rather than all of them. Dramatically reduces compute requirements. This is the practical approach for most organizations.

### Parameter-Efficient Fine-Tuning: LoRA and QLoRA

**LoRA (Low-Rank Adaptation):**

Instead of updating all parameters (billions of values), LoRA adds small trainable "adapter" layers alongside the frozen original weights. The adapters capture the domain-specific adaptation; the original model's knowledge is preserved.

Benefits:
- Train 1–10% of the parameters vs. full fine-tuning
- Dramatically lower compute cost (trainable on a single GPU)
- Multiple LoRA adapters can be swapped in and out on the same base model

**QLoRA (Quantized LoRA):**

Combines LoRA with model quantization, representing weights with fewer bits (4-bit instead of 16-bit). A 70B parameter model that normally requires 8 GPU cards can be trained on a single consumer GPU.

**When to use LoRA vs. QLoRA:**
- LoRA: you have enough GPU memory; want highest quality adaptation
- QLoRA: working with a large model on limited hardware; willing to trade slight quality for accessibility

### Fine-Tuning Workflow

1. **Data preparation**: Collect and format your training examples
   - Format: typically JSONL with prompt-completion pairs
   - Quality matters more than quantity; 1,000 excellent examples outperform 10,000 noisy ones
   - Diversity matters; cover the full range of inputs the model will see in production

2. **Training**: Run fine-tuning using a framework (Hugging Face Transformers, Axolotl, Unsloth)

3. **Evaluation**: Measure performance on a held-out test set
   - Compare to base model performance on the same test set
   - Use both automated metrics and human evaluation

4. **Catastrophic forgetting check**: Verify the model still performs well on general tasks it previously handled; fine-tuning can erode general capabilities

---

## The Decision Framework: Prompt Engineering vs. RAG vs. Fine-Tuning

```
Does the model already know what it needs to know?
  YES → Prompt engineering
  NO → Continue...

Is the knowledge dynamic (updated frequently) or private?
  YES → RAG
  NO → Continue...

Do you need consistent style/format, or specialized reasoning?
  YES → Fine-tuning
  NO → RAG (simpler to maintain)

Do you need both specialized knowledge AND consistent behavior?
  → RAG + Fine-tuning (combined approach)
```

| Approach | Adds Knowledge | Changes Style/Behavior | Update Frequency | Cost |
|---|---|---|---|---|
| Prompt engineering | No | Partially | Instant | Lowest |
| RAG | Yes | No | On document update | Medium |
| Fine-tuning | Yes (baked in) | Yes | Requires retraining | Highest |

---

## Local LLM Deployment

Running AI models locally, on your own hardware rather than via a cloud API, is increasingly viable and valuable.

### Why Run Models Locally?

- **Privacy**: Data never leaves your infrastructure
- **Cost**: After hardware costs, inference is free
- **Offline capability**: No internet required
- **Customization**: Full control over model configuration

### Tools

**Ollama** (Development):
The easiest way to run local LLMs. One command to download and run:
```bash
ollama pull llama3.1:8b
ollama run llama3.1:8b "What is RAG?"
```

Supports most popular open-source models: Llama 3, Mistral, Gemma, Phi-3, Code Llama.

**vLLM** (Production):
High-throughput inference engine for serving models to multiple users. Handles batching, continuous batching, and efficient GPU utilization.

### Hardware Requirements

| Model Size | Minimum VRAM | Recommended Setup |
|---|---|---|
| 7B parameters | 8GB GPU | Consumer GPU (RTX 3080) |
| 13B parameters | 16GB GPU | RTX 3090 / RTX 4090 |
| 34B parameters | 48GB GPU | A6000 or multi-GPU |
| 70B parameters | 80GB GPU | A100 or multiple A6000s |

**Quantization reduces requirements**: A 70B model in 4-bit quantization (QLoRA format) requires ~40GB VRAM vs. ~140GB at full precision.

### Realistic Performance Expectations

Local models are competitive for many tasks but not equivalent to frontier models:
- A locally-run Llama 3 70B ≈ GPT-3.5 quality for most tasks
- Fine-tuned local models can exceed their base quality for domain-specific tasks
- For tasks requiring the latest world knowledge, complex reasoning, or highest accuracy, frontier models via API remain superior

---

## The Hidden Costs of Custom AI

A common mistake: calculating only the visible costs of custom AI (API fees, compute) and missing the ongoing maintenance costs.

| Cost Category | What It Includes |
|---|---|
| **Data pipeline** | Collecting, cleaning, chunking, embedding, and updating your knowledge base |
| **Model maintenance** | Retraining or updating the model as your domain evolves |
| **Evaluation infrastructure** | Automated tests that verify model quality after each update |
| **Operational overhead** | Monitoring, logging, debugging production model behavior |
| **Latency vs. cost trade-off** | Larger, more accurate models cost more; optimizing this requires ongoing work |
| **Model degradation** | Fine-tuned models can "drift" over time as the world changes but the model doesn't |

---

## Hands-On Practice

### Exercise 1: RAG Design

Choose a real knowledge base from your work (a policy document, a product manual, a FAQ, a set of internal guides). Design a RAG system for it:
1. How would you chunk the documents? What size and strategy?
2. Which embedding model would you use?
3. What vector database would you choose (Chroma for local, Pinecone for cloud)?
4. Write the RAG prompt template that would inject retrieved chunks into a query
5. What failure modes are most likely for your knowledge base?

---

### Exercise 2: Ollama Local Deployment

If you have a machine with 8GB+ GPU memory (or CPU fallback):
1. Install Ollama from ollama.ai
2. Pull a model: `ollama pull llama3.1:8b`
3. Run: `ollama run llama3.1:8b "Explain RAG in 3 sentences"`
4. Compare the output to the same prompt on Claude or ChatGPT
5. Evaluate: where does the local model match quality? Where does it fall short?

---

### Exercise 3: Decision Framework Application

For each of these use cases, apply the decision framework to choose between prompt engineering, RAG, and fine-tuning:

1. A legal firm wants an AI that answers questions about their contract templates
2. A customer service team wants consistent, branded responses in a specific tone
3. A hospital wants an AI that knows their internal protocols (updated monthly)
4. A developer wants code completion trained on their proprietary codebase

---

### Exercise 4: Build a Simple RAG System

Using LangChain or LlamaIndex (both have tutorials for beginners):
1. Load a PDF document
2. Chunk it into 512-token segments
3. Create embeddings using OpenAI or a free alternative (sentence-transformers)
4. Store in a local Chroma vector database
5. Build a simple question-answering interface that retrieves relevant chunks and passes them to an LLM

---

## Summary

| Topic | Key Takeaway |
|---|---|
| **Why customize** | Knowledge cut-offs, private data blindness, and narrow-domain hallucination require adaptation beyond prompting |
| **RAG** | Retrieve → Augment → Generate; best for dynamic or private knowledge; no retraining required |
| **Fine-tuning** | Adapts model weights for style, behavior, or specialized reasoning; requires training data and compute |
| **LoRA/QLoRA** | PEFT techniques that make fine-tuning accessible without full GPU cluster budgets |
| **Decision framework** | Prompt engineering first; RAG for knowledge; fine-tuning for behavior; combined for both |
| **Local deployment** | Ollama for development, vLLM for production; privacy and cost benefits; performance trade-offs vs. frontier models |
| **Hidden costs** | Data pipelines, maintenance, evaluation, and monitoring add significant ongoing cost to custom AI |

---

## Next Steps

- Continue to [AI Engineering and Production Systems](ai-engineering.md) to learn how to build robust AI systems at scale
- Experiment with Ollama to run a local model this week
- Design a RAG system for one real knowledge base in your organization
