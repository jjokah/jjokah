# NightCafe Models Guide

Choosing the right AI model for your image: a guide to NightCafe's current model lineup and when each one excels.

---

## What You Will Learn

- Understand what an AI model is and why different models produce different results
- Compare NightCafe's current image models on speed, quality, and best use cases
- Choose the right model based on your specific creative goal
- Understand the difference between standard and PRO models
- Know which models handle text in images, photorealism, anime, and character consistency best

---

## What Is an AI Model?

Every AI image you generate on NightCafe is produced by an underlying model: a large neural network trained on millions of images. The model learns patterns from that training data and uses them to generate new images from your text descriptions.

Different models were trained differently. Some were trained on a broader range of photographic data and produce realistic outputs. Others were optimized for speed. Others learned from artistic or illustrated content and produce more stylized results. Some recent models include architectural improvements that allow them to reason through your prompt before generating, which gives them better composition and spatial understanding.

The practical implication: **the same prompt given to two different models will produce two very different images**. Choosing your model is one of the most important decisions in your generation workflow, separate from writing the prompt itself.

---

## The Current NightCafe Model Lineup

The following table covers the primary image models available in NightCafe as of 2025-2026. NightCafe updates its model offerings regularly, so some newer models may have been added since this guide was written.

| Model | Speed | Max Resolution | Best For | PRO Required? |
|---|---|---|---|---|
| **Nano Banana 2** | ~8 seconds | 4K (upscaled) | Fast prototyping, text in images, everyday generation | No |
| **Nano Banana Pro** | ~25 seconds | Native 4K+ | Character consistency, complex editing, multi-image scenes | Yes |
| **Seedream 4.0** | Fast | 4K | Photorealism, anime characters, cinematic portraits, storyboards | Yes |
| **Flux 2 Klein 4B Fast** | ~1-2 seconds | High | Maximum speed, quick social content, rapid idea testing | No (on Pro plan) |
| **Flux 2 Klein 4B** | ~5-10 seconds | High | Balanced speed and detail, everyday quality work | No (on Pro plan) |
| **Flux 2 Klein 9B** | Slower | High | Maximum detail, fine textures, complex compositions | 1 credit |
| **HiDream I1** | Varies | High | Stylized creative work, imaginative scenes | Yes |

The models you see in the picker may differ slightly based on your account tier. PRO models require an active PRO subscription to generate with.

---

## Nano Banana 2: Speed and Text Accuracy

Nano Banana 2 is NightCafe's fastest high-quality model. It is powered by Google's Gemini 3.1 Flash Image architecture, which means it generates at speed without the usual quality trade-off of earlier fast models.

**Its standout feature is text rendering.** Earlier AI models could not reliably produce readable text inside images. Logos, signs, labels, and typography would come out garbled or illegible. Nano Banana 2 was built specifically to solve this: it understands spatial placement and typography and renders accurate, readable text where you prompt it.

### NB2 vs. NB Pro Comparison

| Feature | Nano Banana 2 | Nano Banana Pro |
|---|---|---|
| Generation speed | ~8 seconds | ~25 seconds |
| Max resolution | 4K (upscaled) | Native 4K+ |
| Text accuracy | High (typography optimized) | Elite |
| Model engine | Gemini 3.1 Flash Image | Gemini 3 Pro Image |
| Character consistency | Good | Excellent |
| Complex editing | Limited | Full |
| PRO required | No | Yes |

**Choose NB2 when:**
- You need images quickly
- Your image contains text (signs, labels, posters, book covers)
- You are prototyping ideas before committing to a final generation
- You are on a free account

---

## Nano Banana Pro: Character Consistency and Editing

Nano Banana Pro (powered by Gemini 3 Pro Image) is the most capable model in NightCafe's lineup for precision work. It uses what NightCafe describes as a "Thinking" process: rather than immediately generating pixels from your prompt, it reasons through your description first, considering physics, lighting, and spatial composition before producing the image.

This architecture gives it two major strengths that simpler models lack:

### 1. Character Consistency

NB Pro keeps a character's identity stable across different poses, scenes, styles, and lighting conditions. If you are creating a comic, a series of product shots, or a set of story illustrations, your character will look like the same person from image to image.

### 2. Complex Editing

NB Pro understands nuanced editing instructions. You can tell it to change the background of an image while preserving the subject's original lighting, or swap a character's outfit without distorting their face. This kind of targeted, local editing is difficult or impossible with simpler models.

**Choose NB Pro when:**
- You are building a multi-image series with the same character
- You need precise in-painting or background replacement
- You need text rendering at the highest possible quality
- You want the most accurate interpretation of a complex prompt

### NB Pro vs. Midjourney (for context)

If you have used Midjourney before, NB Pro competes with it as follows: Midjourney tends to produce more painterly, surreal textures and aesthetic variety. NB Pro excels at editing control, character consistency, and legible text. If you need to lock a character's identity across multiple scenes or perform precise in-painting, NB Pro is the stronger tool.

---

## Seedream 4.0: Photorealism and Anime

Seedream 4.0 is NightCafe's best model for two specific visual modes: **cinematic photorealism** and **anime character work**. It balances both convincingly, and it also supports multi-image inputs, making it useful for consistency workflows and storyboarding.

### What Makes It Different

Seedream 4.0 supports multimodal input. You can:
- Generate from a text prompt at up to 4K resolution
- Edit existing images using natural language instructions
- Upload one to three reference images to guide consistency or transfer a visual style
- Produce multiple images in a single generation with shared characters and unified style

It is particularly strong on faces, skin textures, and expressive emotions. If you are generating portraits, close-up character shots, or detailed anime figures, Seedream 4.0 will typically outperform other models on those subjects.

### How to Access It

1. Go to the **Create page** on NightCafe
2. In the **Model** dropdown, select **Seedream 4.0**
3. Write your prompt with clear subject, action, and environment descriptions (style cues improve results)
4. Optionally, upload one to three reference images to guide consistency

### Prompting Tips for Seedream 4.0

Seedream 4.0 understands natural language well. Clear, specific descriptions outperform long lists of keywords.

| Goal | Example prompt fragment |
|---|---|
| Cinematic portrait | *"Close-up portrait of a young woman with freckles, golden hour light catching her profile, cinematic photography, soft background blur"* |
| Anime character | *"High school student character in a school uniform, walking through cherry blossom petals, anime style, expressive eyes, clean line art"* |
| Storyboard panel | *"A detective enters a dark rainy alley, flashlight cutting through the fog, noir illustration style, dramatic shadows"* |

**Choose Seedream 4.0 when:**
- Your subject is a person, face, or anime character
- You want cinematic photorealism with strong emotional depth
- You are creating multi-panel storyboards or a consistent character series
- You want to combine text-to-image with image-editing in the same workflow

---

## Flux 2 Klein: Three Versions, One Choice

The Flux 2 Klein family comes in three variants, each optimized for a different point on the speed-to-quality spectrum. NightCafe tested all three using the same prompts, evaluating each on prompt coherency, detail and fidelity (hands, textures, lighting), and overall aesthetic quality.

### Flux 2 Klein 4B Fast

Generated in approximately 1-2 seconds. The lighting is surprisingly strong for such a fast model, and textures are clean. Occasional issues with fine details (hands can be slightly off), but not catastrophic for a speed model.

**Best for:** Testing ideas quickly, generating large batches for selection, social media content where speed matters

### Flux 2 Klein 4B (Mid-Tier)

The middle option. Slightly softer lighting than 4B Fast in some cases, but more consistent detail overall. A solid choice for everyday image generation where you want better quality than 4B Fast without paying the time cost of the 9B.

**Best for:** Everyday quality work, backgrounds, environments, and scenes without complex foreground detail

### Flux 2 Klein 9B

The highest-parameter version. Produces the strongest detail, texture, and structural coherence. Worth the extra generation time for final-quality images.

**Best for:** Final renders, detailed fantasy art, architectural and environmental work, anything where fine detail matters

### How to Access Flux 2 Klein Models

In NightCafe Studio, go to: **Create** then **Browse Models**. You will find all three variants listed there. On PRO plans, 4B Fast and 4B are included without extra credit cost.

---

## Model Selection Quick Reference

| Creative goal | Recommended model |
|---|---|
| I want to test an idea fast | Flux 2 Klein 4B Fast |
| I want balanced quality and speed | Nano Banana 2 or Flux 2 Klein 4B |
| My image needs readable text | Nano Banana 2 or Nano Banana Pro |
| I am generating people or faces | Seedream 4.0 or Nano Banana Pro |
| I am creating anime-style art | Seedream 4.0 |
| I need the same character across multiple images | Nano Banana Pro |
| I want the highest detail in a final image | Nano Banana Pro or Flux 2 Klein 9B |
| I want cinematic photorealism with emotion | Seedream 4.0 |
| I am on a free account | Nano Banana 2 or Flux 2 Klein 4B Fast |

---

## Hands-On Practice

### Exercise 1: Same Prompt, Three Models

Write a detailed prompt for a subject of your choice (a person, a landscape, or a fantastical scene). Generate it using three models: Nano Banana 2, Seedream 4.0, and one Flux 2 Klein variant.

Evaluate each result on: accuracy to your prompt, visual quality, and aesthetic appeal. Which model best suited your subject? Would your choice change for a different subject?

---

### Exercise 2: Text-in-Image Test

Write a prompt that includes visible, readable text as part of the image. For example:
> *"A vintage-style poster advertising a fictional seaside café, with the text 'Blue Tide Cafe' at the top, illustrated in art nouveau style, warm coral and navy color palette"*

Generate this with Nano Banana 2 and at least one other model. Evaluate the text legibility in each result. Which model produced the most accurate and readable text?

---

### Exercise 3: Photorealism vs. Anime

Use Seedream 4.0 to generate the same character concept in two styles:
1. Cinematic photorealistic portrait
2. Anime character illustration

Use the same subject description but add the appropriate style modifier for each. How does the model handle the transition between the two visual modes? What stays consistent and what changes?

---

### Exercise 4: Speed vs. Quality Decision

Think about a real use case you have for AI images (social media posts, a presentation, a personal project). Based on how often you need images and what quality level is acceptable, decide:
- Which model tier would you use for everyday drafts?
- Which model tier would you use for final, public-facing images?

Generate one example from each tier using the same prompt. Does the quality difference justify the time or credit cost for your use case?

---

## Summary

| Topic | Key Takeaway |
|---|---|
| **What models are** | Different neural networks trained differently; the same prompt produces different images across models |
| **Nano Banana 2** | Fast, free, strong at text rendering; best starting model for most users |
| **Nano Banana Pro** | Slowest but most capable; "Thinking" architecture gives precise editing and character consistency |
| **Seedream 4.0** | Best for photorealistic faces, anime characters, and multi-panel storyboards |
| **Flux 2 Klein** | Three tiers: 4B Fast for speed, 4B for balance, 9B for maximum detail |
| **Model selection** | Match the model to the goal; no single model is best for everything |

---

## Next Steps

- Continue to [NightCafe Advanced Techniques](nightcafe-advanced-techniques.md) to learn how to use start images, consistent characters, and upscaling
- Return to [AI Image Generation](ai-image-generation.md) to compare NightCafe's models with tools like Midjourney, DALL-E 3, and Adobe Firefly
- Generate one image this week using each of the top three models (NB2, Seedream 4.0, Flux 2 Klein 9B) with the same prompt to build your personal comparison reference
