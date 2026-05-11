# NightCafe Advanced Techniques

Going beyond basic generation: using start images, consistent characters, upscaling, and fine-tuning to take your AI art further.

---

## What You Will Learn

- Use a start image to guide AI generation toward a specific composition or style
- Create and use the Consistent Characters feature to keep the same person, pet, or object across multiple images
- Apply Basic Upscale, Clarity Upscale, and Creative Upscale to enhance image resolution and detail
- Understand when and how to use LoRA fine-tuning models for personalized results
- Combine these techniques into a multi-image storytelling workflow

---

## Start Images: Guiding Generation with a Reference

When you generate from a text prompt alone, the AI starts from random noise and builds an image purely from your description. A **start image** gives the AI a visual foundation to work from before it reads your prompt. The result is a blend of your uploaded image and your text description.

### What Start Images Are Good For

- **Keeping a composition**: You have a rough sketch or a photograph with a layout you like. Upload it and use a prompt to render it in a new style.
- **Style transfer**: Upload a painting you admire and add a prompt to render a new subject in that painting's visual style.
- **Product photography**: Upload a product photo and use a prompt to place it in a more interesting environment.
- **Consistency across edits**: Start with a generated image and use start images combined with a prompt to make targeted changes.

### How to Use a Start Image in NightCafe

1. On the Create page, open **Advanced Settings**
2. Find the **Start Image** section and upload your reference photo or image
3. Adjust the **Strength slider**:
   - Low strength (20-40%): The AI changes the image significantly while loosely following the reference composition
   - High strength (60-80%): The AI preserves more of the original image and makes smaller changes
4. Write your prompt describing what the final image should look like
5. Generate

The strength slider is the most important control here. A higher strength value means the output stays closer to your uploaded image. A lower value gives the AI more creative freedom.

### Practical Example

> Uploaded image: A photo of a coffee mug on a table
> Prompt: *"A ceramic mug on a wooden table in a cozy library, warm candlelight, oil painting style"*
> Strength: 45%

The AI keeps the basic shape and position of the mug but transforms the environment and visual style according to your prompt.

---

## Consistent Characters: The Same Face Across Every Image

One of the most common frustrations with AI art has been character inconsistency. You generate a portrait of a character, then generate another scene with the same character, and the face looks completely different. Hair color, eye shape, facial structure: they shift from image to image.

NightCafe's **Consistent Characters feature** solves this directly. Instead of retraining a model from scratch, you upload a small set of reference photos and NightCafe uses them to anchor your character's appearance across future generations.

### What It Does

You create a saved "character" by uploading up to four reference images. Those images teach the AI what your character should consistently look like. You then reference that character in any prompt using the `@` symbol.

This works for:
- People (including yourself or fictional characters)
- Pets and animals
- Objects (products, props, specific items you want to appear repeatedly)

### How to Create a Consistent Character

1. From the NightCafe Studio, find the **Characters** section (in your profile or the Create area)
2. Click **Create new character**
3. **Upload 1-4 reference images** of your character. More images with varied angles give better consistency.
4. **Name the character** (this becomes the trigger you use in prompts)
5. Save the character

### How to Use the Character in Prompts

In any prompt, type `@` followed by your character's name:

> *"@Alice walking through an enchanted forest, morning light, storybook illustration style"*

> *"@Alice reading a book in a cozy cafe, winter, soft window light, cinematic photography"*

> *"@Alice in a futuristic city, neon lights, night scene, wide shot"*

The character's core appearance stays consistent across all three scenes even though the environment, time of day, and style change.

### What Consistent Characters Enables

For storytellers, comic creators, and brand work, this is the feature that makes multi-image projects possible:

| Use case | How Consistent Characters helps |
|---|---|
| Webcomic or graphic novel | Same character across dozens of scenes and panels |
| Children's book illustration | A child character who looks the same on every page |
| Brand mascot | A recognizable character used across marketing assets |
| Self-portrait series | Your own face consistently rendered in different styles |
| Product photography | The same product photographed in multiple settings |

### Tips for Better Consistency

- Upload reference photos with varied angles (front, three-quarter, side) for better results across different poses
- Use clear, well-lit reference images where the subject is the focus
- If consistency drifts, try uploading one additional reference photo that shows the aspect (e.g., a specific angle) that keeps changing

---

## Upscaling: Enhancing Resolution and Detail

AI-generated images have a native resolution that can look acceptable on screen but insufficient for print, large displays, or close inspection. NightCafe provides three upscaling tools that serve different purposes.

### The Three Upscale Options

| Tool | What It Does | Best For | Key Tip |
|---|---|---|---|
| **Basic Upscale** | Increases resolution and sharpens existing detail | Removing blur; clean enlargement without stylistic change | Start here for most images |
| **Clarity Upscale** | Adds artistic detail while increasing resolution | Adding texture and depth to images that feel flat | Keep creativity setting at 20% or lower |
| **Creative Upscale** | AI re-renders the image with additional realistic detail | Low-detail images that need significant enhancement | Avoid on already-detailed images; it will change them |

### When to Use Each

**Use Basic Upscale** when:
- Your image looks good but is too small or slightly soft
- You want to increase resolution without changing the image's character
- You are preparing an image for print or high-resolution display

**Use Clarity Upscale** when:
- Your image has good composition but the textures feel flat or smooth
- You want more depth and detail added (skin texture, fabric weave, leaf detail)
- You are upscaling a portrait and want richer facial detail

**Use Creative Upscale** when:
- Your image was generated at low quality and needs significant improvement
- You want the AI to actively add elements (background detail, texture) that were absent
- You are working with an older generation that lacks modern quality

### Resolution Settings

For upscale size, **1.5x or 2.0x is the recommended range** for most images. Going to 3x or 4x can make images look artificially smooth, as the AI starts filling in too much information.

For Clarity Upscale specifically, keep the **creativity level at 20% or lower** unless you want the AI to add significant new details. Higher creativity values can introduce elements you did not ask for.

### A Practical Upscaling Workflow

1. Generate your image using any model
2. Inspect the result: is the issue blur, low resolution, or lack of detail?
   - Blur or softness: Basic Upscale at 1.5x
   - Flat textures: Clarity Upscale at 20% creativity, 1.5x
   - Low overall quality: Creative Upscale
3. Compare before and after
4. For important images, apply Basic Upscale first, then evaluate whether Clarity is needed

---

## LoRA and Fine-Tuning: Personalized Model Layers

Fine-tuning allows you to teach NightCafe's base AI model to recognize and reproduce a specific face, object, animal, or visual style. The result is a custom model layer called a LoRA (Low-Rank Adaptation) that you can apply to future generations.

### What Fine-Tuning Does

You provide a set of training images, and NightCafe trains a small model layer that learns the visual characteristics of what you showed it. That layer is then available in your model picker. When you use it in a generation, it pushes the output toward the patterns it learned.

**Use cases:**
- Generate images of your own face in different scenarios and styles
- Recreate a specific pet in imaginary situations
- Replicate the visual style of an artist or design system you want to mimic
- Generate a consistent product in varied environments

### How to Fine-Tune a Model in NightCafe

1. Access **My Models** from the main menu on desktop, or from the profile dropdown on mobile
2. Click **Fine-tune a new model**
3. Choose a **model type**: Face, Object or Animal, or Style
4. Name your model
5. Click **Choose or Create Dataset** and upload your training images
   - Minimum 20 images (more is better)
   - Use diverse images: different angles, lighting, expressions, backgrounds
   - Avoid duplicate or near-identical images
6. Agree to the terms and click **Start Training**
7. Wait 10 to 30 minutes for training to complete (you will receive a notification)
8. Access your trained model from the Model picker in Studio or from **My Models**

### Using Your Fine-Tuned Model

When writing prompts with your LoRA model active, include the trigger word associated with your model (NightCafe provides this when training completes). The trigger word tells the AI to activate the LoRA layer during generation.

**Note:** Fine-tuning is a PRO-only feature, but free users receive **one free face-model tune** and ten generations to try it.

### LoRA vs. Consistent Characters

| Method | Best for | Technical requirement |
|---|---|---|
| **Consistent Characters** | Ongoing storytelling, quick character anchoring, any subject type | Upload 1-4 photos, no training time |
| **Fine-tuning (LoRA)** | Maximum accuracy, specific style replication, extensive use of a character | 20+ images, 10-30 minute training, PRO required |

For most storytelling and creative workflows, Consistent Characters is faster and sufficient. Fine-tuning is the right choice when you need the highest possible fidelity and plan to generate hundreds of images with the same subject.

---

## Putting It Together: A Multi-Image Story Workflow

Here is how to combine these techniques into a complete storytelling workflow:

### Scenario: Creating a three-scene visual story

**Step 1: Create your character**
- Upload 3-4 clear photos of your character to the Consistent Characters feature
- Name her something like "Elara"

**Step 2: Establish the visual style**
- Generate an establishing shot using Seedream 4.0 with a high-quality style prompt
- Example: *"@Elara standing at the edge of a moonlit forest, cinematic fantasy photography, 4K, wide shot, soft rim lighting"*

**Step 3: Generate scene variations**
- Use the same `@Elara` reference in each new scene:
  > *"@Elara discovering a glowing door in an ancient stone wall, close-up, awe on her face, warm golden light from the doorway"*
  > *"@Elara stepping through the doorway into a luminous garden of crystalline flowers, wide shot, magical blue-green light"*

**Step 4: Upscale the final picks**
- Apply Clarity Upscale at 20% creativity to each keeper image for maximum detail
- Export at 2x resolution for print or display use

The result is a three-image story sequence where the same character appears consistently across different scenes, environments, and emotional moments.

---

## Hands-On Practice

### Exercise 1: Start Image Exploration

Find or take a photo that has an interesting composition (a landscape, an architectural space, or even a rough sketch). Upload it as a start image and use a prompt to render it in two different styles:
1. Cinematic photorealism
2. Watercolor or oil painting

Try the same process at 30% strength and 70% strength. How much does the strength slider change the relationship between your reference image and the prompt?

---

### Exercise 2: Consistent Character Series

Create a character using the Consistent Characters feature (use photos of yourself, a friend who has consented, or a printed illustration). Generate that character in three different scenarios:
1. An everyday moment (reading, cooking, walking)
2. A fantastical or unusual setting
3. A different visual style (anime, portrait photography, concept art)

How well does the character's identity hold across the three images? What changes and what stays consistent?

---

### Exercise 3: Upscale Comparison

Generate an image at standard quality. Then apply all three upscale methods to three copies of the same image (Basic, Clarity, and Creative). Compare the results:
- Which method preserved the original image most faithfully?
- Which added the most new detail?
- Which would you use for a final image intended for print?

---

### Exercise 4: Fine-Tune a Style

If you have a PRO account, fine-tune a style model using 20-30 images from a single visual aesthetic you want to replicate (a specific art style, a consistent color palette, a particular illustration look). Test it with five different subject prompts. How consistently does it apply the style? What would you add to the training set to improve it?

For free users: Use Consistent Characters with an object or product instead, and explore how well the same subject can be placed into five different environments using `@` referencing.

---

## Summary

| Topic | Key Takeaway |
|---|---|
| **Start images** | Upload a reference to guide composition; the strength slider controls how closely the AI follows it |
| **Consistent Characters** | Upload 1-4 photos to create a saved character; use `@character-name` in any prompt to anchor its appearance |
| **Upscaling** | Basic for clean enlargement; Clarity for adding texture detail; Creative for low-quality images that need enhancement |
| **LoRA fine-tuning** | Train a custom model layer on 20+ images for maximum fidelity; slower but more accurate than Consistent Characters |
| **Combined workflow** | Start images + Consistent Characters + upscaling together enable coherent multi-scene storytelling |

---

## Next Steps

- Continue to [NightCafe Video Creation](nightcafe-video-creation.md) to learn how to add motion to your images and characters
- Try the Consistent Characters feature this week on a character or object you want to use repeatedly
- If you have a PRO account, run your first fine-tuning session using 20 diverse images of a face, pet, or visual style
