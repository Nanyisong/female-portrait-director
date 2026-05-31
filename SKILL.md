---
name: female-portrait-director
description: Generate, visually expand, optimize, diagnose, and route structured AI image prompts for fictional adult female portraits. Use for lifestyle, curve-focused, fashion, oriental, fantasy, studio, sport, travel, and e-commerce portrait requests; parameter recommendations; prompt rewrites; image-to-prompt preparation; or direct image generation. Preserve explicit user parameters while creating a coherent photography-directed scene.
---

# Female Portrait Director

Turn a small set of portrait parameters into a stable, visually directed, copy-ready image prompt for a fictional adult woman. Expand through visual reasoning, not summary writing or mechanical field filling.

## Required loading order

1. Read [skill/skill.md](skill/skill.md) for the canonical workflow.
2. Read [skill/style-registry.md](skill/style-registry.md). Select exactly one implemented primary route. Do not invent a placeholder extension route.
3. Read only the selected file under `skill/routes/`.
4. Read only the relevant sections of the linked `core/` and `references/` files described by [skill/skill.md](skill/skill.md).

## Operating rules

- Lock explicit user parameters. Expand them without silently replacing them.
- Use the registry as the only routing entry point. Load one primary route and optional compatible overlays only when their files exist.
- Complete age cues, facial features, expression, body direction, pose, clothing, scene, camera, lighting, filter, and platform adaptation before composing the final prompt.
- Build one coherent photographed moment with a time slice, one small event, an action chain, a gaze target, and two or three selective environment details.
- Use route templates as visual direction, not as sentence banks. Do not return a summary or mechanically fill fields.
- Default to fictional, clearly adult subjects. Keep sensual or curve-focused requests non-explicit, clothed, and restrained.
- If the user requests `只要最终提示词`, output only the final prompt and negative constraints.
- If the user requests direct image generation, prepare the directed prompt internally and route it to the available image-generation capability.

## Public references

- Usage guide: [skill/public_instructions.md](skill/public_instructions.md)
- Parameter schema: [skill/parameter_schema.md](skill/parameter_schema.md)
- Safety summary: [docs/prompt_safety.md](docs/prompt_safety.md)
- Examples: [examples](examples)
- Version notes: [docs/versioning.md](docs/versioning.md)

Do not expose unpublished private kernels, hidden fingerprints, or commercial modules.
