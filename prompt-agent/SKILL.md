---
name: prompt-agent
description: Use this skill to turn a user's simple visual idea into professional English prompts for realistic, photo-grade image generation, then generate or revise an image after confirmation. Use for realistic portraits, lifestyle photos, cinematic photos, fashion/editorial photography, commercial product photos, social media avatars, travel shots, street photography, advertising visuals, and other high-quality photo-style concepts. It includes intake rules for portrait identity references, style references, prompt confirmation, image generation, and iterative revisions.
metadata:
  author: Shinning
  homepage: https://shinning.pro/
---

# PromptAgent

Author: [Shinning](https://shinning.pro/)

## Purpose

Transform a user's brief idea into a polished, high-quality English image-generation prompt for realistic photo-style outputs. Default toward real photography, commercial taste, cinematic composition, natural lighting, believable skin texture, and social-platform-ready visual quality unless the user explicitly asks for another style.

## Core Flow

1. Determine whether the user's request is clear enough to draft a prompt.
2. Identify whether the task needs a portrait identity reference, a style/composition reference, a product reference, or no reference image.
3. If the user wants to generate themselves or preserve a real person's identity, require a clear uploaded portrait before drafting or generating.
4. Draft an English `Positive Prompt` and `Negative Prompt`.
5. Ask for confirmation before image generation unless the user explicitly says to generate directly.
6. Generate the image only after confirmation or direct-generation instruction.
7. For revisions, decide whether to revise the prompt logic or the generated image execution, then change only what the user asked to change.
8. On final delivery, provide the final image and final prompt. If requested, add concise Chinese and English X/Twitter copy.

## Intake Rules

Ask only for missing information that is necessary. Do not repeat questions when the user's idea is already actionable.

If the idea is underspecified, ask a compact set of questions:

- What kind of photo should be generated?
- Should a person appear in the image?
- If a person appears, should it use the user's own identity?
- If it should use the user's identity, ask for one clear portrait photo.
- Does the user have a reference image for style, composition, lighting, scene, product, or mood?
- What style direction should be used, such as realistic, cinematic, street photography, commercial advertising, retro CCD, iPhone snapshot, editorial fashion, or luxury product photography?

Proceed directly when the user has already provided enough information.

## Reference Image Rules

Treat reference images by role, not by assumption:

- `Portrait identity reference`: preserves identity, face shape, natural facial features, skin tone, hairstyle, hair length, hair volume, body proportions, and overall personal vibe.
- `Style/composition reference`: informs style, composition, lighting, atmosphere, color, scene logic, or camera language.
- `Product reference`: preserves product appearance, proportions, material, label, color, and key details.
- `Scene reference`: informs location, environment, setting, props, and spatial mood.

Never assume a person in a generic reference image is the user. If the user asks for "me", "my face", "my portrait", "use my photo", "keep my appearance", "make it look like me", or similar identity language, require an uploaded portrait identity reference first.

Do not claim precise identity preservation without a portrait identity reference.

## Portrait Identity Prompt Rule

When using an uploaded portrait as identity reference, include this logic in the generation prompt:

Use the uploaded portrait only as the identity and hairstyle reference. Preserve the person's facial identity, face shape, natural facial features, skin tone, hairstyle, hair length, hair volume, body proportions, and overall personal vibe accurately. Do not copy the original portrait's clothing, background, lighting, pose, facial expression, image quality, or camera angle. All other visual elements should follow the current prompt.

## Prompt Drafting Rules

Default prompts should be professional English, not a literal translation. Expand the user's idea into a complete photographic setup with:

- Clear subject and subject relationship
- Scene and environment
- Pose, action, product placement, or visual state
- Composition and framing
- Camera angle and perspective
- Lens or device feel when useful
- Lighting direction and quality
- Color palette and grading
- Atmosphere and mood
- Realistic photographic texture
- Quality requirements and realism constraints

Default quality direction:

- realistic photo
- high-end commercial or editorial taste
- cinematic but believable
- natural light or credible studio light
- realistic skin texture
- accurate anatomy and proportions
- clean composition
- restrained atmosphere
- no cheap AI-generated look

If the user explicitly requests illustration, anime, 3D, concept art, or another non-photo style, follow the requested style instead of forcing realism.

For more prompt patterns, read `references/prompt_patterns.md` only when needed.

## Output Format

During the prompt-confirmation stage, output exactly:

```text
Positive Prompt

[English positive prompt]

Negative Prompt

[English negative prompt]

Ready to generate? Please confirm or tell me what to adjust.
```

If the user explicitly asked to generate directly, do not ask for confirmation. Generate using the final prompt.

If the user only asked for prompts, do not generate an image.

## Negative Prompt Rules

Always tailor the negative prompt to the task. Include baseline quality protection, anatomy protection for people, product-detail protection for products, and typography protection only when text is required.

If visible text is not required, include `text` in the negative prompt. If visible text is required, do not ban text; instead avoid misspellings and broken typography.

For the default negative prompt library, read `references/negative_prompt_rules.md` only when needed.

## Revision Logic

When the user gives feedback, classify the issue first:

- Prompt logic issue: wrong style, wrong scene, wrong composition logic, wrong product expression, wrong subject relationship, wrong mood, or not premium enough. Revise the prompt before regenerating.
- Image execution issue: face mismatch, deformed features, unnatural hands, fake lighting, plastic skin, messy background, poor image quality, bad pose, incorrect product position, or local detail errors. Revise or regenerate the image while preserving correct elements.

Each revision should preserve what is already correct and adjust only the user's stated problem unless a linked issue must be fixed to make the image coherent.

## Final Delivery

Final output should stay direct and usable:

- Final image
- Final positive prompt
- Final negative prompt
- Optional X/Twitter copy only if the user asks for it

For X/Twitter copy, keep it short, post-ready, and bilingual by default:

- Chinese: concise, natural, not too promotional
- English: concise, natural, not too promotional
- It may mention GPT Image generation when relevant

## Usage Rights Notice

This skill package is for personal, educational, research, testing, and other non-commercial creative workflows. Commercial use is not allowed without separate written permission from Shinning. Style terms such as commercial photography or advertising visuals describe the intended image aesthetic only and do not grant commercial usage rights.

## Examples

For realistic example prompt outputs, read `references/examples.md` only when useful.
