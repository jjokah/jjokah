# AI Video Generation

From text-to-video tools to AI-powered editing: a practical guide to creating professional video content, including a dedicated section on NightCafe's video models and workflows for creators already working in that platform.

---

## What You Will Learn

- Understand how AI video generation works and what it can realistically produce today
- Choose the right tool for different video use cases
- Structure effective text-to-video prompts using the Shot Description Framework
- Build a complete AI video production workflow
- Use AI to accelerate traditional video editing
- Apply AI avatar tools for consistent on-camera presence
- Use NightCafe's video models to animate your images directly within the platform
- Decide when to use NightCafe for video versus a dedicated standalone tool

---

## Part 1: The State of AI Video Today

Video is the most complex content type, combining visual composition, motion, temporal coherence, and audio. AI video generation has advanced faster than almost any other creative technology in recent years.

A few years ago, AI video meant 2 to 4 second clips with strange flickering, unnatural physics, and figures that melted between frames. Today, tools like Sora, Runway Gen-3, and Kling can produce 10 to 30 second clips with cinematic quality, realistic motion, and coherent scene development.

> **Beginner tip:** AI video tools do not require any video editing experience to get started. You describe what you want in text, and the tool generates the clip. The skill to develop is writing good descriptions, not learning video software.

The practical applications are real and growing:

- Marketing teams generate product hero videos without production shoots
- Educators create animated explainer content from scripts
- Small businesses produce social video ads for a fraction of traditional cost
- Enterprises localize video content into multiple languages using AI avatars
- Content creators scale output without equivalent increases in production time

This is not a replacement for professional video production. It is a new category of tool that makes video creation accessible to people and organizations that could never have afforded it before.

---

## Part 2: The AI Video Landscape

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
- Upload a static image and AI generates natural movement within it
- Useful for product shots, portraits, and illustrations
- Tools: Runway, Kling, Pika, Luma all support image-to-video
- Use case: you have a product photo; animate it with subtle motion (rotating, light changes) for a social ad

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

**Use case:** Record yourself once, create an avatar, then use the avatar for all future video content without additional recording sessions.

---

## Part 3: How Text-to-Video Prompting Works

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

The camera movement description often most elevates prompt quality:

| Movement | Description | Effect |
|---|---|---|
| `tracking shot` | Camera follows the subject | Creates dynamic movement and energy |
| `dolly zoom` | Subject stays same size; background changes | Dramatic, psychological effect |
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

## Part 4: A Complete Video Production Workflow

### Phase 1: Strategy and Script

1. **Define the goal**: What should the viewer know, feel, or do after watching?
2. **Script with LLM assistance**:
   > *"Write a 30-second video script for [product/service]. Open with a problem statement. Show the solution in action. End with a clear call to action. Write it as a sequence of shots with narration."*
3. **Create a shot list**: Break the script into individual shots (typically 5 to 10 shots for a 30-second video)

---

### Phase 2: Generate the Clips

For each shot in your shot list:
1. Write a text-to-video prompt using the Shot Description Framework
2. Generate 2 to 3 variations of each shot
3. Select the best variation
4. Note any clips that need image-to-video treatment or avatar treatment

**Batch generation tip:** Use a consistent visual style descriptor in every prompt to maintain coherence across clips:
> *"Cinematic, 4K quality, warm color grading, shallow depth of field"* added to every prompt ensures stylistic consistency across a multi-clip project.

---

### Phase 3: Audio Production

1. Generate voiceover narration (ElevenLabs or Murf; see the [AI Audio Generation](ai-audio-generation.md) guide)
2. Generate background music matched to mood and length (Mubert, Soundraw)
3. Source or generate sound effects if needed

---

### Phase 4: Edit and Assemble

1. Import all clips and audio into your editor (CapCut, Premiere, DaVinci Resolve)
2. Arrange clips in sequence; trim to match narration timing
3. Add transitions; keep them minimal for a professional look
4. Add auto-captions (CapCut AI, Descript, or Veed.io); critical for social media where video is often watched on mute
5. Add your logo, lower thirds, and any text overlays in Canva or within the editor
6. Export in appropriate aspect ratios (16:9 for YouTube, 9:16 for TikTok and Reels, 1:1 for feed posts)

---

### Phase 5: Multi-Format Publishing

Use AI to adapt your core video for multiple platforms in one session:
- **YouTube**: Full 16:9 version with chapters in description
- **LinkedIn**: 1:1 square crop, captions always on, under 3 minutes
- **Instagram Reels and TikTok**: 9:16 vertical, first 3 seconds must hook immediately
- **Twitter/X**: 16:9 or 1:1, under 2:20, captions on

CapCut's Auto Reframe feature handles the aspect ratio conversions automatically.

---

## Part 5: AI Avatar Videos

AI avatar tools let you create talking-head videos without sitting in front of a camera.

### When to Use Avatars

**Best for:**
- High-volume internal training content (onboarding, compliance, process videos)
- Multilingual localization (the avatar speaks in multiple languages from the same script)
- Consistent product explainer videos at scale

**Not ideal for:**
- Deeply personal or emotional communication (customer relationships, leadership messages)
- Any content where audience trust hinges on knowing a real person is speaking

### Workflow with HeyGen

1. Create your avatar: either a pre-built template or upload 2 minutes of your own recorded video to create a personal avatar
2. Paste your script into HeyGen's script editor
3. Select language (HeyGen supports 175+ languages and will lip-sync appropriately)
4. Choose background (solid color, your brand template, or custom environment)
5. Generate and download

For enterprise localization: upload your English script, HeyGen translates it, then generates localized video with the avatar speaking in each language with appropriate lip sync.

---

## Part 6: Responsible Use of AI Video

### Disclosure Requirements

> **Warning:** AI-generated video, especially avatar video using someone's likeness, carries significant ethical and emerging legal responsibilities.

- **Disclose AI generation**: Label AI-generated video content, especially if it features realistic people or speaks on behalf of a real person
- **Consent for likeness**: Never generate video content using someone's likeness without their explicit consent
- **No impersonation**: Creating AI video of real public figures in realistic scenarios is deceptive and potentially illegal
- **Deepfake risk**: The same technology that creates avatar videos can be used to create non-consensual content; this is a serious harm to avoid and actively oppose

### Watermarking and Provenance

- Major platforms are adopting the Coalition for Content Provenance and Authenticity (C2PA) standard for content provenance
- Tools like Sora and major video platforms are beginning to embed invisible watermarks in AI-generated content
- YouTube, LinkedIn, and TikTok all have policies requiring labeling of AI-generated content

---

## Part 7: NightCafe Video Creation

If you are already using NightCafe to generate images, you can animate those images directly within the same platform without switching tools, managing exports, or learning a new interface.

### What NightCafe Video Can Do Now

NightCafe's video models now produce clips with:
- Smooth, natural motion
- Consistent lighting across the clip
- Expressive character movement
- Cinematic scene dynamics
- Synced audio (in select models)

> **The key advantage for NightCafe users:** You can generate a still image on NightCafe, then animate it in the same session without leaving the platform. This makes image-to-video the most natural starting point.

---

### NightCafe's Video Model Lineup

| Model | Best For | Key Strength |
|---|---|---|
| **VO 3.1** | Cinematic storytelling, dramatic scenes | Realism, expressive motion, synced sound; community favorite |
| **VO 3.1 Fast** | Brainstorming and draft iterations | Same quality profile as VO 3.1 but faster and cheaper |
| **Kling 2.5 Turbo Pro** | Refined, polished sequences | Full creative control, ultra-smooth motion, versatile |
| **Kling 2.5 Standard** | Quick experiments, lightweight projects | Balance of speed and quality for lower-stakes content |
| **Seed Dance 1.0 Pro** | Rich, detailed scenes | Strongest depth and visual complexity for final-quality clips |
| **Seed Dance 1.0 Pro Fast** | Rapid iteration at near-Pro quality | Similar output to Pro at faster speed; useful for storyboarding |
| **Seed Dance 1.0 Lite** | Looping animations and playful experiments | Great entry point for beginners; simple and forgiving |
| **PixVerse V5** | Expressive, stylized, and artistic motion | Creative and imaginative output; distinctive visual character |

#### VO 3.1: The Community Favorite

VO 3.1 became the most popular video model on NightCafe shortly after its launch. It delivers realism, dramatic lighting, expressive character motion, and synced sound. If your goal is cinematic storytelling, VO 3.1 is the model that feels closest to actual film production.

**VO 3.1 Fast** produces the same visual style at reduced cost and time. Many experienced NightCafe creators use Fast mode for concept testing and switch to the full VO 3.1 for final clips.

#### Seed Dance: Three Tiers for Different Workflows

- **Lite** is the best starting point for beginners. It is forgiving with prompts, inexpensive, and good for looping animations and short experiments.
- **Pro Fast** is for creators who want near-Pro quality on a tighter time budget.
- **Pro** delivers the deepest detail and visual complexity for final-quality outputs.

#### Kling 2.5: Control and Smoothness

Kling 2.5 Turbo Pro is the best choice when you want precise, ultra-smooth motion with full creative control. Particularly strong for refined sequences where you need consistency across a longer clip.

#### PixVerse V5: Artistic and Expressive

PixVerse V5 produces motion that is more stylized and creatively distinctive than the other models. It is the best choice when you want AI video that looks intentionally artistic rather than photorealistic.

---

### Prompting for NightCafe Video

The most common beginner mistake in video prompting is writing the same kind of prompt you would use for an image: describing what the scene looks like. Video prompts need to describe **what moves and how**.

#### The Video Prompt Structure

```
Subject:       Who or what is in the scene?
Action:        What are they doing? (be specific and continuous)
Environment:   Where is this happening?
Camera:        How is the camera behaving? (tracking shot, static, push-in)
Motion quality: Fast / slow / smooth / abrupt?
```

#### Weak vs. Strong Video Prompts

**Weak:** *"A woman in a forest."*

**Strong:** *"A woman in a flowing white dress walks slowly through an ancient fog-covered forest, camera tracking behind her at shoulder height, soft golden light filtering through the trees, slow motion, cinematic"*

The strong version tells the model: who is there, what they are doing (walking slowly), how the camera is positioned (tracking behind), and the quality of the motion (slow motion).

---

### NightCafe Motion Vocabulary

These terms reliably influence how NightCafe's video models handle movement:

| Term | Effect |
|---|---|
| `slow motion` | Stretches the movement, creates dramatic, contemplative feel |
| `tracking shot` | Camera follows the subject through the scene |
| `static camera` | No camera movement; subject moves within a fixed frame |
| `push in` | Camera slowly moves toward the subject |
| `pull back` | Camera slowly moves away, revealing more of the environment |
| `smooth motion` | Signals the model to avoid jerky or abrupt movement |
| `looping animation` | Useful for Seed Dance Lite; the clip repeats seamlessly |
| `cinematic` | Applies film-like color grading and composition sensibility |

#### Real Prompt Examples from the NightCafe Community

These are the kinds of prompts that have produced strong results:

> *"Long shot of a friendly creature in a warmly decorated room, sipping from a large mug, pointing at the mug after each sip, slow and gentle movement, cozy lighting"*

> *"Black carousel spinning with skeletal horses, glowing pumpkins serving as lanterns, flickering flames, night scene, eerie atmosphere, slow rotation"*

> *"Glowing fish swimming around an illuminated treasure chest on the ocean floor, light refracting through the water, gentle swaying of the fish, deep blues and greens"*

Notice that each prompt describes continuous motion, a clear subject, and a mood or atmosphere. None of them simply describe what the scene looks like at a single moment.

---

### The Image-to-Video Workflow in NightCafe

The most useful video workflow for NightCafe image creators is **image-to-video**: generate a still image first, then animate it. This lets you use your best image prompting skills to perfect the composition, then add motion on top.

**When to use image-to-video:**
- You have a high-quality image and want to bring it to life
- You want precise control over the composition before adding motion
- You are animating a product shot, portrait, or scene illustration
- You want the Consistent Characters feature to carry into video (generate the character image first, then animate)

**Image-to-video workflow in NightCafe:**
1. Generate your image using any image model (or upload an existing image)
2. Open the image from your NightCafe gallery
3. Look for the **Animate** option or the video generation button
4. Choose your **video model** from the dropdown
5. Write a **motion prompt** describing what should move and how
6. Select the **clip length** if options are available
7. Generate

The AI uses your image as the visual foundation and adds motion according to your prompt.

**Tips for better image-to-video results:**
- Use a clean, well-composed image as your source; complex or cluttered images are harder for the model to animate coherently
- Keep your motion prompt focused on one or two moving elements rather than trying to animate everything at once
- For character animations, focus the motion on the face, hands, or a specific gesture rather than full-body movement
- If the result has artifacts or unwanted motion, try a more specific prompt: instead of *"she moves"*, write *"she turns her head slowly to the right, looking toward the camera"*

---

### NightCafe Video vs. Standalone Video Tools

NightCafe is not always the right tool for video. Here is an honest comparison:

**When to use NightCafe for video:**
- You are already using NightCafe for images and want a seamless workflow
- You need short clips (under 15 to 20 seconds) for social media, presentations, or b-roll
- You want to animate a NightCafe image you have already generated
- You are experimenting and want to stay within a single platform
- You want to submit video to NightCafe Daily Challenges

**When to use a dedicated video tool instead:**
- You need clips longer than 20 to 30 seconds
- You are building a multi-scene video with complex narrative continuity
- You need precise audio synchronization beyond what NightCafe's synced-sound models offer
- You need specific features like avatar generation (HeyGen, Synthesia) or advanced editing workflows (Runway, Descript)

---

## Hands-On Practice

### Exercise 1: Shot Description Practice

Choose a 30-second ad or video clip you admire. Watch it with the sound off and describe each shot using the Shot Description Framework (Subject, Action, Setting, Camera, Style). How specific would your description need to be to recreate this clip?

---

### Exercise 2: Text-to-Video First Test

Use a free or trial tier of Runway, Pika, or Luma Dream Machine to generate your first AI video clip.

Start with this prompt:
> *"A single red apple sitting on a wooden table in a sunlit kitchen. Slow, gentle rotation of the apple. Static camera. Warm, natural lighting. Photorealistic, shallow depth of field. 5 seconds."*

Evaluate: What did the AI generate well? Where did it fail? What would you change in the prompt?

---

### Exercise 3: Shot-by-Shot Production

Plan a 3-shot, 15-second promotional video for something you work on. Write:
1. A shot list (3 shots with timing)
2. A text-to-video prompt for each shot using the Shot Description Framework
3. Generate each clip and assemble them in a basic editor (iMovie or CapCut)

What worked? What needed regeneration?

---

### Exercise 4: NightCafe First Video Clip

Generate a simple still image on NightCafe using any image model. Then animate it using Seed Dance 1.0 Lite. Write a simple motion prompt (5 to 10 words describing what moves and how).

Evaluate: What did the model animate well? What looked unnatural? What would you change?

---

### Exercise 5: Three NightCafe Models, Same Clip

Choose a text-to-video prompt (a landscape scene, an object in motion, or a simple character action). Generate the same prompt using three different video models: VO 3.1, one Kling variant, and one Seed Dance variant.

Compare: Which produced the smoothest motion? Which had the most cinematic quality? Which would you use for a social media post versus a professional presentation clip?

---

### Exercise 6: Full NightCafe Image-to-Video Workflow

Using the image-to-video approach:
1. Generate a high-quality image using a detailed prompt (use Seedream 4.0 or NB Pro for best results)
2. Animate it using VO 3.1 or Kling 2.5 with a targeted motion prompt
3. Download the clip and view it alongside the original still image

What did the animation add to the image? What was lost in translation from still to moving image?

---

## Summary

| Topic | Key Takeaway |
|---|---|
| **Text-to-video tools** | Sora for highest quality; Runway for creativity; Kling for realism; Luma for longer clips; Pika for social media |
| **Shot Description Framework** | Subject, Action, Setting, Camera, Style: all five needed for professional prompts |
| **Workflow** | Strategy, script, generate clips, audio, edit, multi-format publish |
| **AI avatars** | High-ROI for training and localization; must disclose AI generation; never use without consent |
| **Ethics** | Disclose AI generation, respect consent requirements, follow platform policies |
| **NightCafe video models** | VO 3.1 for cinematic quality; Kling 2.5 for smoothness; Seed Dance Lite for beginners; PixVerse for artistic style |
| **NightCafe prompting** | Describe what moves and how, not just what the scene looks like; use motion vocabulary |
| **Image-to-video** | Generate a still image first for compositional control, then animate it |
| **NightCafe vs. standalone tools** | NightCafe for short clips and integrated workflows; dedicated tools for long-form and professional production |

---

> **Next steps:** Continue to [Module 4: AI for Development](../module-4-ai-for-development/vibecoding-intro.md) to learn how AI is changing how software is built. Or return to [AI Image Generation](ai-image-generation.md) to deepen your NightCafe image skills before applying them to video.
