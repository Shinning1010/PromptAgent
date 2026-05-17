# PromptAgent

Author: [Shinning](https://shinning.pro/)

PromptAgent is a Codex skill for turning simple visual ideas into polished, production-ready prompts for realistic, photo-grade image generation.

It is designed for creators who want better image-generation results without writing long photography prompts from scratch. The skill helps clarify intent, distinguish portrait identity references from style references, produce professional English prompts, and guide image revisions until the result is usable.

## What It Does

- Turns short image ideas into detailed English image prompts
- Produces both positive and negative prompts
- Defaults to realistic, photo-grade, cinematic, commercial-quality visuals
- Supports portraits, lifestyle photos, product photography, street photography, travel photos, social media avatars, editorial fashion, and advertising-style visuals
- Requires a clear portrait upload before attempting identity-preserving images
- Separates portrait identity references from style, composition, product, and scene references
- Supports prompt refinement and image revision workflows

## Example Use Cases

- "Create a cinematic rainy-night portrait of me."
- "Turn this into a luxury perfume product photo prompt."
- "Generate an iPhone-style summer cafe selfie."
- "Make a realistic editorial fashion street photo."
- "Create a premium X/Twitter-ready visual from this idea."

## How The Skill Works

The skill follows a structured workflow:

1. Understand the user's idea.
2. Check whether the request needs a portrait identity reference.
3. Ask for a clear portrait photo when the user wants to preserve their own identity.
4. Identify any reference image as identity, style, composition, product, or scene reference.
5. Draft a professional English positive prompt and negative prompt.
6. Ask for confirmation before image generation, unless the user explicitly requests direct generation.
7. Generate or revise the image while preserving correct elements.
8. Provide the final image and final prompt. Optional X/Twitter copy can be generated on request.

## Installation

Clone or download this repository, then place the `prompt-agent` folder into your Codex skills directory.

Example:

```text
~/.codex/skills/prompt-agent
```

Then invoke it in Codex with:

```text
Use $prompt-agent to turn my photo idea into a professional image-generation prompt.
```

## Skill Structure

```text
prompt-agent/
  SKILL.md
  agents/
    openai.yaml
  references/
    prompt_patterns.md
    negative_prompt_rules.md
    examples.md
```

## Important Identity Rule

This skill does not claim to generate a real person accurately without an uploaded portrait identity reference.

If a user asks for "me", "my face", "my portrait", "use my photo", "keep my appearance", or similar identity-preserving generation, the skill must first request a clear portrait image. A generic style reference image is not treated as the user's identity.

## Who Can Use It

This project may be used for personal, educational, research, testing, and other non-commercial creative workflows.

Commercial use is not allowed without separate written permission from Shinning. This includes, but is not limited to, selling the skill, bundling it into paid products or services, using it for paid client work, using it in commercial image-generation workflows, or redistributing it for commercial benefit.

The terms "commercial-quality", "commercial photography", "advertising-style", or similar wording inside the skill describe an image aesthetic only. They do not grant commercial usage rights.

## License

This project is released for non-commercial use under the [PolyForm Noncommercial License 1.0.0](https://polyformproject.org/licenses/noncommercial/1.0.0).

Commercial use is not permitted without separate written permission from the author.

Required Notice: Copyright (c) 2026 Shinning (https://shinning.pro/)

## Author

Created by [Shinning](https://shinning.pro/).
