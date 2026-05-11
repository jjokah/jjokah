# NightCafe Prompting Guide

How to write AI art prompts that produce consistent, high-quality results: a practical formula for beginners, built from the techniques of NightCafe's top creators.

---

## What You Will Learn

- Understand why prompt specificity determines image quality
- Apply the seven-element prompt formula used by top NightCafe creators
- Write story-driven prompts that describe moments, not just objects
- Use negative prompts to eliminate unwanted elements from your images
- Use the Prompt Magic feature to automatically enhance basic prompts
- Build a reusable reference of style modifiers for different creative goals

---

## Why Most Beginners Get Generic Images

Type *"a dragon"* into any AI image generator and you will get something competent and completely forgettable. It will look like the average of every dragon image the model has ever seen. The AI is not being lazy. It is doing exactly what you asked: producing the most likely visual match for a vague description.

This is the core insight behind good prompting: **AI image models default to the statistical average of their training data**. Your job as a creator is to pull the output away from that average and toward something specific and intentional.

The difference between a beginner's result and a top creator's result is almost always the prompt, not the model.

> "NightCafe was the first tool where AI art finally started making sense for me, because once I understood how to describe what I actually wanted, the results stopped surprising me in bad ways." -- from the NightCafe community

---

## The Seven-Element Prompt Formula

Top NightCafe creators, including long-time community ambassador TWNightingale, consistently use a seven-element structure for their prompts. This is not a rigid formula to follow mechanically; it is a checklist that ensures you have covered every dimension of the image before generating.

```
1. Subject:     Who or what is the main focus?
2. Setting:     Where is this happening?
3. Mood:        What emotion or atmosphere should the image convey?
4. Lighting:    What kind of light? (golden hour, studio, overcast, neon)
5. Details:     Specific textures, colors, clothing, facial expressions
6. Style:       Photorealistic / anime / watercolor / oil painting / cinematic
7. Camera feel: Close-up / wide shot / overhead / shallow depth of field
```

You do not need all seven in every prompt. But the more elements you specify, the more intentional your result will be.

### Weak vs. Strong Prompt Examples

| Weak prompt | Strong prompt using seven elements |
|---|---|
| *"A woman in a forest"* | *"A young woman in a flowing white dress standing in an ancient mossy forest, late afternoon, warm golden light filtering through the canopy, intricate embroidery on her sleeves, cinematic photography, medium shot, shallow depth of field"* |
| *"A coffee shop"* | *"Cozy corner of an independent cafe, morning, soft warm light through rain-streaked windows, steam rising from a ceramic mug, empty notebook open on the table, watercolor illustration, slightly top-down angle"* |
| *"A dragon"* | *"A massive silver dragon perched on a clifftop above storm clouds at night, lightning illuminating its scales from below, dramatic contrast, intense and ancient mood, hyperrealistic fantasy art, wide low-angle shot"* |

The strong versions do not just list more words. They make every element intentional: the character, the environment, the emotional register, the light source, the medium, and the framing.

---

## TWNightingale's Approach to Soft Magic

NightCafe creator and community ambassador TWNightingale developed what she calls the "Soft Magic" style: ethereal, warm-toned imagery that feels cinematic and emotionally resonant. Her approach applies the seven-element formula with a focus on atmospheric lighting and specific natural details.

Her prompt formula in practice:

```
[Specific subject with detail] + [Intimate setting] + [Warm or dreamlike mood] +
[Natural light source: golden hour / sunrise / candlelight] +
[Texture details: fabric, petals, mist] +
[Style: cinematic photography / storybook] + [Camera: close-up or medium shot]
```

**Example:**
> *"A young woman with windswept hair sitting on a mossy stone bridge over a misty stream, sunrise, soft golden light catching the dewdrops on nearby wildflowers, wearing a sage-green linen dress, cinematic portrait photography, medium close-up, warm pastel tones"*

This produces results that are consistent and recognizable as a style, not just a random generation. The goal is to develop your own version of this approach.

---

## Story-Driven Prompts: Describing Moments

One of the most effective shifts you can make as a prompt writer is to stop describing objects and start describing moments.

**Objects:** *"a fantasy world, a dragon, a castle"*

**A moment:** *"a child reading a book as the room transforms around her into a glowing forest world, dragons emerging from the open pages, a single candle on the desk still burning"*

The second version describes something happening. There is a subject, an action, a transformation, and an emotional beat. The AI has far more to work with, and the result will feel like a scene rather than a catalog of elements.

### The Moment-Building Structure

Use this four-part structure when you want a narrative or story-driven image:

```
Subject:        Who is in the scene?
Action:         What is happening right now?
Environment:    Where does this take place?
Transformation: What is changing, breaking, appearing, or emerging?
```

**Example using this structure:**
> *"An astronaut (subject) floating in zero gravity, reaching toward a glowing anomaly (action), inside the cargo bay of a derelict space station (environment), as golden light pours through the fractured hull and refracts into dozens of tiny rainbows (transformation). Cinematic. Wide shot. Deep shadows and warm accent light."*

---

## Negative Prompts

A negative prompt tells the AI what you do NOT want in the image. This is just as important as your positive description, especially for correcting common issues.

### How to Add Negative Prompts in NightCafe

1. On the Create page, open **Advanced Settings**
2. Find the **Negative Prompt** field
3. Type a comma-separated list of elements to exclude

### Common Negative Prompt Terms

```
blurry, low quality, distorted, deformed hands, extra fingers,
watermark, text overlay, signature, stock photo pose,
oversaturated, harsh shadows, artificial smile,
multiple faces, duplicate, tiling, ugly, noisy
```

### When to Use Negative Prompts

- **People images**: Add *"deformed hands, extra fingers, asymmetrical face"* to reduce the most common AI artifacts
- **Clean product shots**: Add *"busy background, shadows, watermark, text"*
- **Natural scenes**: Add *"artificial, CGI, rendered, plastic"* if you want real-looking environments
- **Style enforcement**: If your image keeps drifting toward a style you do not want (e.g., too cartoonish), add that style to the negative prompt

You do not need a long negative prompt to start. Three to five targeted terms are more effective than a generic list of fifty.

---

## Prompt Magic

NightCafe includes a feature called **Prompt Magic** that automatically expands your basic prompt with additional style details and quality keywords. It is designed for users who are just starting out and are not yet confident writing detailed prompts.

### What Prompt Magic Does

You type a simple description like *"a lighthouse at dusk"* and Prompt Magic enhances it to something like *"a lighthouse at dusk, golden hour light, cinematic photography, 4K, detailed, soft warm tones"* before sending it to the model.

### When to Use It

- **Just starting out**: Prompt Magic is a good training tool. Use it, then look at what it added to your simple description. Over time you will learn which additions improve results.
- **Quick experiments**: When you want to test a concept fast without writing a full prompt
- **Comparing results**: Generate once with Prompt Magic on and once with it off to see the difference

### When to Turn It Off

- **Precise creative control**: When you have a specific style in mind and do not want the AI adding generic quality terms that dilute your intent
- **Style work**: When you are developing a signature look, you want full control over every element

---

## Style Modifier Reference

These are the most useful modifiers to add to prompts for different goals. Think of them as vocabulary you can mix and match.

### Quality and Resolution

| Modifier | Effect |
|---|---|
| `highly detailed` | Encourages fine textures and intricate elements |
| `4K` / `8K` | Signals high-resolution output |
| `photorealistic` | Pushes toward realistic photography look |
| `sharp focus` | Reduces blur and softness |
| `professional photography` | Clean, controlled, well-composed |

### Lighting

| Modifier | Effect |
|---|---|
| `golden hour` | Warm, soft, late afternoon or early morning light |
| `dramatic lighting` | High contrast, strong directional light |
| `soft diffused light` | Even, flattering, no harsh shadows |
| `neon lighting` | Colorful urban night atmosphere |
| `candlelight` | Intimate, warm, slightly flickering ambiance |
| `backlit` | Subject silhouetted or rimlit against bright background |

### Style and Medium

| Modifier | Effect |
|---|---|
| `cinematic photography` | Film-like color grading, letterbox feel |
| `watercolor illustration` | Soft, fluid, artistic brushwork |
| `anime style` | Stylized characters with large eyes and expressive features |
| `oil painting` | Rich, textured, classical art look |
| `flat design illustration` | Minimal, clean, icon-like |
| `concept art` | Detailed, world-building, often used for fantasy or sci-fi |

### Camera and Composition

| Modifier | Effect |
|---|---|
| `close-up` | Face or detail fills the frame |
| `wide shot` | Full scene with environment context |
| `overhead / bird's eye view` | Looking straight down at the subject |
| `low angle` | Looking up at the subject, making it appear powerful |
| `shallow depth of field` | Subject sharp, background blurred |
| `rule of thirds` | Subject placed off-center for natural composition |

---

## Hands-On Practice

### Exercise 1: The Seven-Element Ladder

Choose a simple subject: a house, a person, an animal, or a natural scene. Generate four versions of it, adding one layer of the seven-element formula at a time:

1. Subject only: *"A lighthouse"*
2. Subject + Setting + Lighting: *"A lighthouse on rocky cliffs, stormy night, lightning in the distance"*
3. Add Mood + Details: *"...isolated and foreboding mood, barnacles on the base, crashing waves"*
4. Add Style + Camera feel: *"...oil painting style, wide dramatic shot, dark sky with one shaft of light"*

Compare the four images. At which step did the quality improve most dramatically?

---

### Exercise 2: Moment vs. Object

Pick a theme (adventure, loss, celebration, discovery). Write two prompts:
1. A static object description: list three to five things associated with the theme
2. A moment description: describe a scene where something is happening, someone is present, and there is a visible emotion or action

Generate both and compare. Which feels more like art and which feels more like a stock photo? What does the difference tell you about how you should write future prompts?

---

### Exercise 3: Negative Prompt Correction

Generate an image of a person doing something in a busy environment. Inspect the result for common artifacts: distorted hands, awkward poses, stock photo feel. Write a targeted negative prompt addressing exactly what you see. Regenerate and compare. How effectively did the negative prompt correct the issues?

---

### Exercise 4: Build Your Style Reference

Write a "style signature" prompt: a set of modifiers that you will add to every prompt to create a consistent visual identity. Choose:
- One lighting style
- One style or medium
- One camera feel
- Two to three quality terms

Test it on five different subjects. Does the visual identity stay consistent across different content? What adjustments improve consistency?

---

## Summary

| Topic | Key Takeaway |
|---|---|
| **Why specificity matters** | AI defaults to the average of its training data; you pull it away from generic with specific descriptions |
| **Seven-element formula** | Subject, Setting, Mood, Lighting, Details, Style, Camera feel: use as a checklist, not a rigid template |
| **Moment-driven prompts** | Describe what is happening, not just what exists; Subject + Action + Environment + Transformation |
| **Negative prompts** | Tell the model what to exclude; three to five targeted terms are more useful than a long generic list |
| **Prompt Magic** | A useful training tool for beginners; turn it off when you want precise creative control |
| **Style modifiers** | Quality, lighting, medium, and camera terms are the vocabulary of prompt writing; build your own reference |

---

## Next Steps

- Continue to [NightCafe Models Guide](nightcafe-models-guide.md) to understand which model to pair with each type of prompt
- Read [AI Image Generation](ai-image-generation.md) for a deeper look at the Art Director mindset and how it applies across all AI image tools
- Write five prompts using the seven-element formula this week, one for each different style modifier category
