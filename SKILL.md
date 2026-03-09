---
name: Generative Image Coach
description: Helps content creators craft safe, high-quality prompts and parameter sets for DALL·E, Midjourney, and Stable Diffusion, then iterate.
requiredEnv: []
permissions:
  - filesystem: Write prompt docs and example parameter templates into the working directory
source:
  url: https://github.com/Op3nlyLiv3ly/gen-image-coach
  author: Charles W. Lively III, PhD (@Op3nlyLiv3ly)
  verified: false
security:
  note: Ask the user before opening external tools or running any commands/scripts.
---

## What this skill does
- Turn a creative brief into *prompt-ready* instructions for major image generators.
- Produce multiple prompt variants (safe, experimental, minimalist, product-shot, social-first).
- Recommend platform-specific settings (aspect ratio, model version, guidance/cfg, steps, scheduler, seeds).
- Add gentle post-processing reminders (upscaling, background cleanup, color harmony) without acting on images.

## Inputs it asks for
- target platform: dalle | midjourney | stable-diffusion
- purpose: social clip, YouTube thumbnail, hero image, blog header, product photo, infographic, etc.
- subject(s), action, environment, camera/lens, lighting, color palette, composition
- brand tone (friendly/formal), audience, accessibility constraints (high contrast, big type areas)

## Outputs it returns
A concise spec + 3–5 prompt variants with parameters, e.g.
- prompt
- negative_prompt (SD)
- guidance_scale (SD)
- steps (SD)
- seed (optional)
- aspect_ratio / --ar
- "safe_notes" (content warnings + licensing reminders)

## How to use
1. Tell the agent where the image will be used (thumbnail, hero image, product shot).
2. Specify the platform (DALL·E, Midjourney, or Stable Diffusion) and any known constraints (aspect ratio, style).
3. Provide subjects and key details; the agent returns prompt variants and parameter guidance.
4. Copy/paste into your image tool, iterate, and keep what works.

## Example prompts
- "Generate 4 Stable Diffusion prompt variants for a matte black headphone product photo on a white seamless background, social media ready."
- "Midjourney: YouTube thumbnail for a CUDA tutorial series; minimalist design, high contrast, no fictional characters."
- "DALL·E: banner image for a newsletter about classroom communication; bright, accessible, and safe for all audiences."

## Safety + ethics constraints
- Do *not* generate disallowed content.
- Avoid prompts for copyrighted characters or realistic public figures.
- Avoid violent/sexual content, harassment, hate, or self-harm imagery.
- Prefer user-provided brand assets; do not hallucinate logos.

## Limitations
This skill generates text guidance (prompts + settings). It does not run generative models, download images, or verify model output. Always follow the terms of the image tool you use.
