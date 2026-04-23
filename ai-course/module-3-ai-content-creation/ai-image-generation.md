# AI Image Generation

How to think like an Art Director when prompting AI: creating professional-quality visuals, understanding the tools available, and knowing when each is the right choice.

---

## What You Will Learn

- Understand how diffusion models turn text descriptions into images
- Apply the Art Director mindset to write effective image generation prompts
- Structure prompts using the Subject/Style/Brand framework
- Use negative prompting to eliminate unwanted elements
- Choose the right image generation tool for your specific use case
- Identify and correct common visual artifacts

---

## How Image Generation Works (Enough to Use It Well)

AI image generators are powered by **diffusion models**. They work by:

1. Starting with a field of random visual noise, essentially static
2. Iteratively refining that noise, guided by the text prompt, until a coherent image emerges
3. The process repeats across hundreds of refinement steps, each moving the image closer to what the prompt describes

Think of it as a sculptor starting with a featureless block and gradually revealing a form, guided entirely by your description.

What this means in practice:
- **Every generation is unique**: Two identical prompts produce different images
- **Specificity matters enormously**: Vague prompts produce average, generic images; specific prompts produce targeted visuals
- **The model interprets, not calculates**: It doesn't look up your description; it generates what is statistically likely to match it based on its training

---

## Choosing the Right Tool

| Tool | Best For | Notable Strength | Limitation |
|---|---|---|---|
| **Midjourney** | High-end artistic and photorealistic images | Aesthetic quality; lighting; cinematic style | No free tier; requires Discord; less controllable for specific layouts |
| **DALL-E 3** (ChatGPT) | Specific, instruction-following images; text in images | Highest prompt adherence; integrates with ChatGPT conversation | Less artistic range than Midjourney |
| **Adobe Firefly** | Commercial-safe marketing assets | Trained on licensed content; integrates with Photoshop/Illustrator | Less cinematic; best for clean, design-focused images |
| **Stable Diffusion** | Custom workflows; local deployment; full control | Open-source; runs locally; extensible with LoRA models | Requires technical setup; steeper learning curve |
| **Ideogram** | Images containing readable text | Best text-in-image quality available | Less photorealistic than Midjourney |
| **Canva AI** | Quick visuals within a design workflow | Integrated into Canva; easy for non-designers | Less powerful than dedicated generators |

**Decision guide:**
- Need high-quality hero images or editorial art → **Midjourney**
- Need specific layout or text in the image → **DALL-E 3** or **Ideogram**
- Need commercial-safe assets for marketing → **Adobe Firefly**
- Need readable text overlaid in the image → **Ideogram**
- Building a custom pipeline with your own model → **Stable Diffusion**

---

## The Art Director Mindset

Most people approach image generation by describing what they want: *"A person working at a computer."* They get a generic, unremarkable image and wonder why AI isn't impressive.

Art directors think differently. They don't just describe the subject; they specify the complete visual experience:
- What is the subject doing, and what mood does it convey?
- What is the lighting: natural, studio, golden hour, overcast?
- What is the composition: wide shot, close-up, overhead, eye-level?
- What is the color palette: warm neutrals, cool blues, high-contrast?
- What is the visual style: photorealistic, editorial illustration, watercolor?
- Who is the photographer, artist, or director whose style you're referencing?

The shift from "person at computer" to a full Art Director brief produces a fundamentally different image.

---

## The Prompt Structure: Subject / Style / Brand

Break every image prompt into three layers:

### Layer 1: Subject and Composition

Describe the main subject specifically: what they're doing, their expression, their position in the frame, the setting.

**Weak:** *"A business meeting."*

**Strong:** *"Four professionals gathered around a glass conference table, one standing and pointing at a large monitor showing a colorful bar chart. Late afternoon. Modern office with floor-to-ceiling windows overlooking a city. Candid moment, mid-conversation."*

**Composition keywords that direct the camera:**
- `wide shot` / `close-up` / `medium shot` / `overhead / bird's eye view` / `low angle`
- `rule of thirds` / `centered composition` / `shallow depth of field`
- `environmental portrait` (subject in their space) / `isolated subject on clean background`

---

### Layer 2: Style and Aesthetics

Tell the model *how* to render the image: the visual language.

**Photography styles:**
- `photorealistic, DSLR photography`: general photorealism
- `editorial photography`: journalistic, documentary feel
- `corporate stock photo`: clean, accessible, designed for business use
- `cinematic photography, anamorphic lens`: movie-like quality

**Illustration styles:**
- `flat design illustration`: minimal, icon-like
- `isometric illustration`: 3D-looking diagrammatic style
- `watercolor illustration`: soft, artistic
- `line art`: single-color outlines

**Lighting keywords:**
- `natural light, golden hour`: warm, soft, flattering
- `overcast lighting`: diffused, even, no harsh shadows
- `studio lighting, three-point lighting`: professional, controlled
- `dramatic chiaroscuro`: high-contrast, dark and moody
- `neon backlighting`: colorful, futuristic

**Color palette keywords:**
- `warm earth tones` / `cool blues and greys` / `pastel color palette`
- `monochromatic` / `high contrast black and white`
- Specific color: `teal and orange color grading` (popular cinematic palette)

---

### Layer 3: Brand Keywords

Add any brand-specific constraints:

- Color constraints: *"Color palette restricted to navy, white, and gold."*
- Style constraints: *"Clean, minimal, professional, consistent with corporate design."*
- What to avoid: *"No people. No text. No shadows on white background."*

---

## Negative Prompting

Many tools support **negative prompts**: a list of elements you explicitly don't want in the image. This is as important as the positive prompt.

**Common negative prompt elements:**
```
blurry, low quality, distorted, extra fingers, deformed hands,
watermark, text overlay, signature, photobomber in background,
oversaturated, harsh shadows, motion blur, noise, grain
```

**In Midjourney:** add `--no [element]` at the end of your prompt
**In DALL-E / Stable Diffusion:** add a "Negative prompt" field in the interface

**Example full prompt with negative:**
```
Prompt: "A diverse team of four engineers reviewing code on large monitors 
in a bright modern tech office. Natural lighting. Wide shot. 
Candid, documentary-style photography. Canon R5, 35mm lens."

Negative: "stock photo pose, cheesy smile, everyone looking at camera, 
blurry, watermark, text overlay, distorted faces"
```

---

## Style Reference Techniques

### Reference Photographers and Artists

AI models have learned from vast archives of photography and art. Referencing specific photographers or visual styles gives you immediate, consistent aesthetic control.

**Photography references:**
- `in the style of Ansel Adams`: dramatic black and white landscape
- `Annie Leibovitz portrait style`: intimate, editorial celebrity photography
- `National Geographic photography`: documentary, environmental
- `Helmut Newton style`: high-contrast, dramatic fashion

**Art direction references:**
- `Bauhaus design aesthetic`: geometric, functional, minimal
- `Art Nouveau`: organic curves, decorative, nature-inspired
- `Swiss International Style`: clean grids, typography-forward

**Film/color grade references:**
- `color grading inspired by Blade Runner 2049`: teal/orange, dystopian
- `Wes Anderson color palette`: pastel symmetrical compositions

---

## Identifying and Correcting Visual Artifacts

AI-generated images have characteristic failure modes. Inspect these areas before using any image:

**Hands and fingers:**
- Count the fingers; AI frequently generates 6 or more
- Check for merged fingers, impossible bends, or extra joints
- Solution: regenerate, or use inpainting to fix specific areas

**Faces:**
- Look for asymmetry, multiple overlapping features, or "melting" appearance
- Solution: face restoration tools (Adobe Photoshop Generative Fill, Midjourney's "vary region")

**Text in images:**
- Letters that don't form words, inconsistent fonts, blended characters
- Solution: use Ideogram (best text accuracy) or DALL-E 3; add text in Canva or Figma afterward

**Backgrounds:**
- Impossible geometry, objects that float or have no shadows
- Solution: use a clean background prompt ("isolated on white background") or regenerate

**Semantic blending:**
- Two objects merging in unnatural ways (shirt pattern continues onto skin, etc.)
- Solution: be more specific about the boundary between objects in your prompt

---

## Building a Visual Brand System

For organizations using AI image generation consistently, establish a visual prompt template:

```
[Subject and composition] + [Lighting: natural light, golden hour] +
[Style: corporate editorial photography, Canon R5 quality] +
[Color: warm earth tones, neutral backgrounds] +
[Brand constraints: diverse representation, no stock-photo poses] +
[Negative: watermark, text overlay, blurry, distorted]
```

Save this template and prepend it to every image prompt. The result is a coherent visual language across your AI-generated assets.

---

## Hands-On Practice

### Exercise 1: The Specificity Ladder

Run this sequence with an image generator (DALL-E 3 or Adobe Firefly):

1. *"A business professional."*
2. *"A business professional in a modern office."*
3. *"A woman in her 40s, South Asian, smiling confidently, standing in a glass-walled open-plan office. Business casual. Natural light from large windows behind her. Editorial photography style."*
4. Add a negative prompt: *"No stock photo pose, no looking directly at camera, no artificial smile."*

Compare the four images. What changed? At which level did the quality step-change most dramatically?

---

### Exercise 2: Style Exploration

Take the same subject (a technology concept of your choice) and generate it in four completely different visual styles:
1. `Photorealistic photography`
2. `Flat design illustration`
3. `Watercolor painting`
4. `Isometric 3D illustration`

Which style best fits your brand's visual identity? Why?

---

### Exercise 3: Artifact Inspection

Generate five images using a prompt that includes people. For each image:
1. Inspect the hands: how many fingers?
2. Inspect the faces: any distortion or asymmetry?
3. Inspect the background: any impossible geometry?

Document what you find. What percentage of images required correction before use?

---

### Exercise 4: Brand Template

Design a visual prompt template for your personal or organizational brand:
1. Choose a consistent lighting style
2. Choose a consistent photography or illustration style
3. Choose a consistent color palette
4. Write your negative prompt

Test the template on five different subjects. How consistent is the visual language across the outputs?

---

## Summary

| Topic | Key Takeaway |
|---|---|
| **How it works** | Diffusion models refine random noise into images guided by your text description; specificity directly determines quality |
| **Tool selection** | Match the tool to the use case: Midjourney for quality, DALL-E 3 for accuracy, Firefly for commercial safety, Ideogram for text in images |
| **Art Director mindset** | Subject + composition, style + aesthetics, and brand constraints are all three needed in every professional prompt |
| **Negative prompts** | Tell the model what NOT to generate; equally important to the positive prompt |
| **Artifacts** | Inspect hands, faces, text, and backgrounds before use; use inpainting or specialized tools to correct |

---

## Next Steps

- Continue to [AI Audio and Voice](ai-audio-and-voice.md) to add spoken content to your creative toolkit
- Build your first visual brand template and test it on five different subjects
- Try generating one professional image for a real project this week using the Subject/Style/Brand framework
