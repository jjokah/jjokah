# Machine Learning Foundations

A conceptual primer on Machine Learning: what it is, how it works, and what the key terms mean, without requiring a mathematics background.

---

## What You Will Learn

- Explain the three main types of machine learning (supervised, unsupervised, reinforcement)
- Describe the training and inference cycle in plain language
- Understand what transformers are and why they matter
- Define key terms: parameters, tokens, embeddings, context window, fine-tuning
- Map ML concepts to the AI products and systems you already use

---

## Why Technical Practitioners Need to Understand ML

You don't need to implement a neural network to work effectively with AI. But you do need to understand enough to:
- Make informed decisions about when to use AI and which approach is right
- Understand why AI systems behave the way they do
- Communicate clearly with engineers and data scientists
- Evaluate vendor claims about model capabilities
- Anticipate failure modes before they become production incidents

This guide provides that foundation: the concepts without the calculus.

---

## What Machine Learning Is

Traditional programming works like this: you give a computer explicit rules, and it applies those rules to data to produce output.

```
Rules + Data → Output
```

Machine learning reverses this:

```
Data + Output (examples) → Rules (learned automatically)
```

Instead of writing rules by hand, you show the system thousands (or billions) of examples of inputs and their correct outputs. The system figures out the rules on its own, a process called **training**.

> **Analogy:** Teaching a child what a dog is. You don't define a dog as "four legs + fur + bark." You show them pictures of dogs and say "dog," show them pictures of cats and say "cat," and after enough examples, they can correctly identify dogs in photos they've never seen. Machine learning works the same way, except instead of a child's brain, it's a mathematical model.

---

## The Three Types of Machine Learning

### Supervised Learning

**How it works:** The model is trained on labeled examples: inputs paired with correct outputs.

**Example:** Training an email classifier:
- Input: email text
- Label: "spam" or "not spam"
- Training: show the model millions of labeled emails
- Result: a model that classifies new emails with high accuracy

**Common applications:** image classification, fraud detection, credit scoring, demand forecasting, sentiment analysis

**What "supervised" means:** A human supervisor provides the correct labels during training.

---

### Unsupervised Learning

**How it works:** The model is trained on unlabeled data. It finds patterns, groups, and structures on its own.

**Example:** Customer segmentation:
- Input: customer behavior data (purchase history, browsing patterns)
- No labels provided
- Training: the model discovers that customers naturally cluster into groups (deal-seekers, brand loyalists, occasional buyers)
- Result: actionable customer segments that weren't predefined

**Common applications:** recommendation systems, anomaly detection, topic modeling, data compression

**What "unsupervised" means:** No human labels; the model discovers structure independently.

---

### Reinforcement Learning (RL)

**How it works:** An agent learns by taking actions and receiving rewards or penalties. It learns to maximize cumulative reward over time.

**Example:** Game-playing AI (AlphaGo):
- Agent: the AI player
- Actions: where to place a stone on the board
- Reward: +1 for winning, -1 for losing
- Training: millions of self-play games
- Result: a player that surpasses human world champions

**Modern AI application: RLHF (Reinforcement Learning from Human Feedback):**
This is how modern LLMs like Claude and ChatGPT are made to be helpful. After initial training on text data, human raters evaluate the model's responses. The model is trained to produce responses that humans rate highly.

> **Key Insight:** The "helpfulness" of Claude and ChatGPT is not a property of the base model; it is learned through RLHF. This is why earlier language models were capable of generating text but not reliably helpful.

---

## The Training and Inference Cycle

### Training

Training is the process of creating a model from data. For a large language model:

1. **Collect data**: Trillions of words from the internet, books, and code
2. **Initialize**: Create a model with random weights (parameters)
3. **Forward pass**: Feed text through the model; it predicts the next word
4. **Compare to truth**: Measure how wrong the prediction was (the loss)
5. **Backward pass (backpropagation)**: Adjust every parameter slightly to reduce the error
6. **Repeat**: Do this billions of times across the training dataset

After training is complete, the model's parameters are frozen. The training process is complete.

**Training a frontier model:**
- GPT-4: estimated thousands of A100 GPU-hours
- Llama 3 (405B): 30.84 million GPU-hours
- Training cost: hundreds of millions of dollars for frontier models

Training a model from scratch is not something individuals or most organizations do. You use pre-trained models and customize them.

---

### Inference

Inference is using the trained model to make predictions; it is what happens every time you send a message to an AI chatbot.

1. **Input**: Your message is converted to tokens
2. **Forward pass**: Tokens are processed through the model's layers
3. **Output**: The model predicts the next most likely token
4. **Repeat**: The model generates one token at a time, using its previous output as new input
5. **Result**: A sequence of tokens is assembled into the response you see

**Key inference concepts:**
- **Latency**: How long the model takes to start responding (time to first token)
- **Throughput**: How fast it generates tokens (tokens per second)
- **Context window**: How much text the model can "see" at once (input + output combined)

---

## Key Terms Decoded

### Parameters

Parameters are the numerical values learned during training, the "weights" of the neural network. They encode everything the model has learned from its training data.

- GPT-2 (2019): 1.5 billion parameters
- GPT-3 (2020): 175 billion parameters
- Estimated frontier models today: 1 trillion+ parameters (not publicly disclosed)

More parameters generally means more capacity to learn complex patterns, but also more compute required for training and inference.

> **Misconception:** More parameters does not simply mean "smarter." Architecture, training data quality, and training techniques all matter enormously. Some smaller models outperform larger ones on specific tasks.

---

### Tokens

A token is the unit of text that the model processes, roughly 0.75 words on average.

- "Hello, world!" → 4 tokens: ["Hello", ",", " world", "!"]
- A typical English word ≈ 1.3 tokens
- 1,000 tokens ≈ 750 words ≈ about 3 pages of text

Tokens matter for two practical reasons:
1. **Pricing**: AI APIs charge by token (input and output separately)
2. **Context window**: Models have a maximum token limit for their entire input + output

---

### Context Window

The context window is the maximum amount of text (in tokens) that a model can process in a single interaction. Everything inside the context window is what the model "knows" for that conversation.

| Model | Context Window |
|---|---|
| GPT-4o | 128,000 tokens (~96,000 words) |
| Claude 3.5 Sonnet | 200,000 tokens (~150,000 words) |
| Gemini 1.5 Pro | 1,000,000 tokens (~750,000 words) |

**Practical implications:**
- Very long documents (books, codebases) may need to be chunked or summarized to fit
- Conversation history accumulates tokens; very long conversations may eventually exceed the window
- More context allows more sophisticated reasoning over more material

---

### Embeddings

An embedding is a mathematical representation of text (or images, audio, etc.) as a vector of numbers, a list of floating-point values.

**Why it matters:**
- Embeddings capture *meaning*, not just words
- Texts with similar meanings have similar embeddings (are "close" in vector space)
- This is how semantic search works: find documents whose embeddings are close to your query's embedding

> **Example:** "The dog ran fast" and "The canine sprinted quickly" have very different words but very similar embeddings, because they mean nearly the same thing.

**Applications:**
- Semantic search (find documents by meaning, not keyword matching)
- RAG systems (retrieve relevant chunks from a knowledge base)
- Recommendation systems (find similar items)
- Duplicate detection (find similar support tickets)

---

### The Transformer Architecture

Virtually all modern AI models (GPT, Claude, Gemini, LLaMA, BERT, Stable Diffusion) are built on the **transformer** architecture, introduced in the 2017 paper "Attention Is All You Need."

The key innovation: **self-attention**. Instead of processing text sequentially (word by word), transformers process all tokens simultaneously and learn which tokens should "pay attention" to which other tokens.

**What self-attention enables:**
- Understanding that "it" in "The cat sat on the mat because it was soft" refers to "mat," not "cat," even though they're far apart
- Capturing long-range dependencies in text
- Parallel processing of all tokens simultaneously (dramatically faster training)

You don't need to understand the mathematics. What matters: transformers can model complex relationships between words and ideas at a scale that earlier architectures could not.

---

## From Concepts to Practice

### How These Concepts Appear in Real Systems

| Concept | Where You See It |
|---|---|
| **Supervised learning** | Email spam filter, fraud detection, image search |
| **Reinforcement learning** | RLHF in ChatGPT and Claude: why they're helpful |
| **Parameters** | "GPT-4 is a large model": large refers to parameter count |
| **Tokens** | "This document is 8,000 tokens": determines cost and feasibility |
| **Context window** | "The context window is full": need to chunk the document |
| **Embeddings** | "Semantic search" in Notion AI, GitHub Copilot's codebase understanding |
| **Transformer** | Every modern LLM: it's the universal architecture |

---

## Hands-On Practice

### Exercise 1: Tokenization

Visit platform.openai.com/tokenizer. Paste different types of text and observe:
1. How many tokens is a 500-word document?
2. How does code tokenize differently from prose?
3. How does non-English text tokenize compared to English?

What implications does this have for cost and context window usage?

---

### Exercise 2: Embedding Intuition

Describe in your own words what it means for two pieces of text to have "similar embeddings." Come up with three pairs of sentences that should be semantically close, and three pairs that should be semantically far apart, even if they share words.

Now test your intuition: use Cohere's free embedding API or the OpenAI embeddings playground to compute similarity scores for your pairs.

---

### Exercise 3: Training vs. Inference

For each of these AI scenarios, identify whether it is a training or inference operation:
1. ChatGPT responding to your question
2. OpenAI improving GPT-4 based on user feedback
3. Your Spotify recommendation loading
4. A spam filter classifying a new email
5. A researcher fine-tuning Llama on medical data

---

### Exercise 4: Context Window Calculation

You want to analyze a legal document that is 120 pages long. A typical page has ~250 words.

1. Estimate the token count
2. Which models could fit this in their context window in a single call?
3. If using a model with a 32,000-token context window, how would you need to chunk the document?

---

## Summary

| Concept | Key Takeaway |
|---|---|
| **Machine learning** | Systems that learn rules from data, rather than being explicitly programmed |
| **Supervised learning** | Labeled examples teach the model to classify or predict |
| **Unsupervised learning** | Model finds patterns in unlabeled data |
| **Reinforcement learning** | Learning through trial, error, and reward: how LLMs become helpful via RLHF |
| **Parameters** | The numerical weights that encode what the model has learned; more isn't always better |
| **Tokens** | The unit of text processing; determines pricing and context limits |
| **Embeddings** | Numerical representations of meaning: enable semantic search and RAG |
| **Transformers** | The architecture behind virtually all modern AI models; self-attention is the key innovation |

---

## Next Steps

- Continue to [RAG and Model Customization](rag-and-model-customization.md) to learn how to adapt pre-trained models for specific use cases
- Explore the tokenization tool at platform.openai.com/tokenizer to build intuition about context costs
- Read the abstract of "Attention Is All You Need" (2017), the most influential paper in modern AI
