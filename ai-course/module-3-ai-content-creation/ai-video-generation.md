# AI Video Generation

From text-to-video tools to AI-powered editing: a practical guide to creating professional video content without a traditional production team.

---

## What You Will Learn

- Understand how AI video generation works and what it can realistically produce today
- Choose the right tool for different video use cases
- Structure effective text-to-video prompts using the Shot Description Framework
- Build a complete AI video production workflow
- Use AI to accelerate traditional video editing
- Apply AI avatar tools for consistent on-camera presence without constant recording

---

## The State of AI Video in 2024–2025

Video is the most complex content type, combining visual composition, motion, temporal coherence, and audio, and AI video generation is advancing faster than any other generative modality.

Two years ago, AI video was characterized by 2–4 second clips with strange motion artifacts and unnatural physics. Today, tools like Sora, Runway Gen-3, and Kling can produce 10–30 second clips with cinematic quality, realistic motion, and coherent scene development.

The practical applications are real and growing:

- **Marketing teams** generate product hero videos without production shoots
- **Educators** create animated explainer content from scripts
- **Small businesses** produce social video ads for a fraction of traditional cost
- **Enterprises** localize video content into multiple languages using AI avatars
- **Content creators** scale output without equivalent increases in production time

This is not a replacement for professional video production. It is a new category of tool that makes video creation accessible to people and organizations that could never have afforded it before.

---

## The AI Video Landscape

### Text-to-Video Tools

These tools generate video clips from text descriptions:

| Tool | Clip Length | Quality Level | Best For |
|---|---|---|---|
| **Sora** (OpenAI) | Up to 60 seconds | Highest: cinematic motion and coherence | Complex scenes, narrative clips, high-quality marketing |
| **Runway Gen-3 Alpha** | Up to 10 seconds | Excellent: creative and stylized | Creative campaigns, abstract and stylized video |
| **Kling 1.5** (Kuaishou) | Up to 30 seconds | Very high: realistic physics | Realistic scenes, product videos, human motion |
| **Luma Dream Machine** | Up to 120 seconds | High: especially good motion | Longer clips, smooth motion, b-roll footage |
| **Pika 2.0** | Up to 15 seconds | Good: strong for social media | Social media content, quick ads, stylized clips |
| **Hailuo / MiniMax** | Up to 6 seconds | Very high: especially faces | Close-up shots, person-focused content |

### Image-to-Video Tools

These tools animate a still image:
- Upload a static image → AI generates natural movement within it
- Useful for product shots, portraits, and illustrations
- Tools: Runway, Kling, Pika, Luma all support image-to-video
- **Use case:** You have a product photo; animate it with subtle motion (rotating, light changes) for a social ad

### AI Video Editing Tools

These tools accelerate traditional video editing:

| Tool | Primary Function |
|---|---|
| **Descript** | Transcript-based editing; edit video by editing text; AI voice correction |
| **CapCut AI** | Auto-captions, auto-reframe, AI background removal, viral template generation |
| **Adobe Premiere AI** | Generative Extend (fill gaps), Enhance Speech, Auto Reframe |
| **Veed.io** | Online editor with auto-subtitles, translations, and AI video enhancement |

### AI Avatar Tools

These tools create realistic video of a digital human speaking:

| Tool | Best For |
|---|---|
| **HeyGen** | Professional avatar videos with branded backgrounds; most realistic |
| **Synthesia** | Enterprise-grade training and onboarding videos |
| **D-ID** | Animating still photos to speak |
| **Captions.ai** | Faster avatar creation with auto-editing |

**Use case:** Record yourself once → create an avatar → use the avatar for all future video content without additional recording sessions

---

## How Text-to-Video Prompting Works

Unlike image generation where you describe a single frame, video prompting must describe a scene that unfolds over time. This requires a different mental model.

### The Shot Description Framework

Structure every text-to-video prompt across five dimensions:

```
1. Subject:     Who or what is in the shot?
2. Action:      What are they doing? (specific and continuous)
3. Setting:     Where does this happen?
4. Camera:      What is the shot type and camera movement?
5. Style:       What is the visual aesthetic?
```

**Weak prompt:** *"A person walking in a city."*

**Strong prompt:** *"A young professional woman in a navy blazer walks confidently down a busy urban street, sunlight filtering through trees. Slightly behind her, tracking shot. She glances up at a skyscraper. Cinematic, warm afternoon light, shallow depth of field, golden hour. Slow motion. Documentary realism."*

---

### Camera Movement Vocabulary

The camera movement description is often the element that most elevates prompt quality:

| Movement | Description | Effect |
|---|---|---|
| `tracking shot` | Camera follows the subject | Creates dynamic movement and energy |
| `dolly zoom` (Vertigo effect) | Subject stays same size; background changes | Dramatic, psychological effect |
| `slow push in` | Camera slowly moves toward subject | Builds tension or intimacy |
| `orbit / 360 spin` | Camera circles the subject | Product showcase, reveals |
| `crane shot` | Camera rises up from ground level | Epic, cinematic openings |
| `handheld` | Slight camera shake | Realism, documentary feel |
| `static shot` | No camera movement | Stable, composed, formal |

---

### Temporal Coherence: Describing Motion Over Time

Describe what happens in sequence, not just what the scene looks like:

**Good temporal description:**
> *"The scene begins with a close-up of coffee being poured into a cup. Steam rises. The camera slowly pulls back to reveal a cozy kitchen, morning light streaming through a window. A person's hands wrap around the mug. The camera continues pulling back to show them looking out the window, a slight smile forming."*

Think of your prompt as a storyboard description, covering each beat of the scene.

---

## A Complete Video Production Workflow

### Phase 1: Strategy and Script

1. **Define the goal**: What should the viewer know, feel, or do after watching?
2. **Script with LLM assistance**:
   > *"Write a 30-second video script for [product/service]. Open with a problem statement. Show the solution in action. End with a clear call to action. Write it as a sequence of shots with narration."*

3. **Create a shot list**: Break the script into individual shots (typically 5–10 shots for a 30-second video)

---

### Phase 2: Generate the Clips

For each shot in your shot list:
1. Write a text-to-video prompt using the Shot Description Framework
2. Generate 2–3 variations of each shot
3. Select the best variation
4. Note any clips that need image-to-video (animated product shots) or avatar treatment

**Batch generation tip**: Use a consistent visual style descriptor in every prompt to maintain coherence across clips:
> *"Cinematic, 4K quality, warm color grading, shallow depth of field"*, added to every prompt, ensures stylistic consistency across a multi-clip project

---

### Phase 3: Audio Production

1. Generate voiceover narration (ElevenLabs or Murf; see Module 3, Audio guide)
2. Generate background music matched to mood and length (Mubert, Soundraw)
3. Source or generate sound effects if needed

---

### Phase 4: Edit and Assemble

1. Import all clips and audio into your editor (CapCut, Premiere, DaVinci Resolve)
2. Arrange clips in sequence; trim to match narration timing
3. Add transitions; keep them minimal for professional look
4. Add auto-captions (CapCut AI, Descript, or Veed.io); critical for social media where video is often watched on mute
5. Add your logo, lower thirds, and any text overlays in Canva or within the editor
6. Export in appropriate aspect ratios (16:9 for YouTube, 9:16 for TikTok/Reels, 1:1 for feed posts)

---

### Phase 5: Multi-Format Publishing

Use AI to adapt your core video for multiple platforms in one session:
- **YouTube**: Full 16:9 version with chapters in description
- **LinkedIn**: 1:1 square crop, captions always on, under 3 minutes
- **Instagram Reels / TikTok**: 9:16 vertical, first 3 seconds must hook immediately
- **Twitter/X**: 16:9 or 1:1, under 2:20 minutes, captions on

CapCut's Auto Reframe feature handles the aspect ratio conversions automatically.

---

## AI Avatar Videos

AI avatar tools let you create talking-head videos without sitting in front of a camera.

### When to Use Avatars

**Best for:**
- High-volume internal training content (onboarding, compliance, process videos)
- Multilingual localization (the avatar speaks in multiple languages from the same script)
- Consistent product explainer videos at scale
- Content creators who want to separate their on-camera time from their publishing volume

**Not ideal for:**
- Deeply personal or emotional communication (customer relationships, leadership messages)
- Any content where audience trust hinges on knowing a real person is speaking
- Situations where AI disclosure would damage credibility

### Workflow with HeyGen

1. Create your avatar: either a pre-built template or upload 2 minutes of your own recorded video to create a personal avatar
2. Paste your script into HeyGen's script editor
3. Select language (HeyGen supports 175+ languages and will lip-sync appropriately)
4. Choose background (solid color, your brand template, or custom environment)
5. Generate and download

For enterprise localization: upload your English script → HeyGen translates → generates localized video with the avatar speaking in each language with appropriate lip sync

---

## Responsible Use of AI Video

### Disclosure Requirements

> **Warning:** AI-generated video, especially avatar video using someone's likeness, carries significant ethical and emerging legal responsibilities.

- **Disclose AI generation**: Label AI-generated video content, especially if it features realistic people or speaks on behalf of a real person
- **Consent for likeness**: Never generate video content using someone's likeness without their explicit consent
- **No impersonation**: Creating AI video of real public figures in realistic scenarios is deceptive and potentially illegal
- **Deepfake risk**: The same technology that creates avatar videos can be used to create non-consensual content; this is a serious harm to avoid and actively oppose

### Watermarking and Provenance

- Major platforms are adopting the Coalition for Content Provenance and Authenticity (C2PA) standard for content provenance
- Tools like Sora and major video platforms are beginning to embed invisible watermarks in AI-generated content
- Follow platform guidelines on AI content disclosure; YouTube, LinkedIn, and TikTok all have policies requiring labeling of AI-generated content

---

## Hands-On Practice

### Exercise 1: Shot Description Practice

Choose a 30-second ad or video clip you admire. Watch it with the sound off and describe each shot using the Shot Description Framework (Subject, Action, Setting, Camera, Style). Then compare your description to what you actually see: how specific would your description need to be to recreate this clip?

---

### Exercise 2: Text-to-Video First Test

Use a free or trial tier of Runway, Pika, or Luma Dream Machine to generate your first AI video clip.

Start with this prompt:
> *"A single red apple sitting on a wooden table in a sunlit kitchen. Slow, gentle rotation of the apple. Static camera. Warm, natural lighting. Photorealistic, shallow depth of field. 5 seconds."*

Evaluate: What did the AI generate well? Where did it fail? What would you change in the prompt to improve it?

---

### Exercise 3: Shot-by-Shot Production

Plan a 3-shot, 15-second promotional video for something you work on. Write:
1. A shot list (3 shots with timing)
2. A text-to-video prompt for each shot using the Shot Description Framework
3. Generate each clip and assemble them in a basic editor (even iMovie or CapCut)

Evaluate: What worked? What needed regeneration? What would you do differently?

---

### Exercise 4: AI Editing Test

Find a raw video clip (record yourself on your phone, or use a Creative Commons video). Use CapCut AI or Descript to:
1. Auto-generate captions
2. Remove background noise
3. Trim silences automatically

How much editing time did AI save?

---

## Summary

| Topic | Key Takeaway |
|---|---|
| **Text-to-video tools** | Sora for highest quality; Runway for creativity; Kling for realism; Luma for longer clips; Pika for social media |
| **Shot Description Framework** | Subject + Action + Setting + Camera Movement + Visual Style: all five needed for professional prompts |
| **Workflow** | Strategy → Script → Generate clips → Audio → Edit → Multi-format publish |
| **AI avatars** | High-ROI for training and localization; must disclose AI generation; never use without consent |
| **Ethics** | Disclose AI generation, respect consent requirements, follow platform policies |

---

## Next Steps

- You have completed Module 3. You now have a full multimedia content creation toolkit.
- Continue to [Module 4: AI for Development](../module-4-ai-for-development/vibecoding-intro.md) to learn how AI is changing how software is built
- Try generating one text-to-video clip using the Shot Description Framework this week
- Evaluate whether AI avatar videos could replace or supplement any high-volume video content your organization produces
