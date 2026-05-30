[English](README.md) | [简体中文](README_zh.md) | [日本語](README_ja.md) | [한국어](README_ko.md)

# Female Portrait Prompt Director Skill

Female Portrait Prompt Director Skill is a structured prompt-generation system for AI image creation. It supports clean lifestyle portraits, restrained curve-focused lifestyle portraits, urban fashion photography, gufeng fantasy portraits, and e-commerce clothing model images. The system includes parameter locking, style routing, facial-feature modules, body-shape modules, camera and lighting completion, and negative-constraint optimization to help users generate stable, compliant, and reusable AI image prompts from simple inputs.

This project is not a generic prompt collection. It is an extensible female portrait prompt Skill framework.

## Project Scope

Generate complete prompts from a small set of input parameters. Preserve the user's explicit requirements while completing facial features, body shape, camera direction, lighting, filters, platform purpose, and negative constraints. Subjects must be clearly adult women. Outputs emphasize realistic photography, restrained expression, and stable generation.

## Supported Styles

- Clean lifestyle portraits
- Restrained curve-focused lifestyle portraits
- Urban fashion photography
- Gufeng fantasy portraits
- E-commerce clothing model images

## Core Capabilities

- Lock user-specified parameters and only refine or stabilize them.
- Route each request through the appropriate style template and avoid conflicting style keywords.
- Complete facial differentiation, body shape, camera, lighting, filters, and negative constraints automatically.
- Support prompt generation, prompt optimization, failure diagnosis, parameter recommendations, and review-friendly rewrites.
- Preserve clothing-display priority for e-commerce images and explicit safety boundaries for curve-focused portraits.

## Quick Start

When using this repository as a Codex Skill, invoke `$female-portrait-director`. Minimal example:

```text
Style: clean lifestyle portrait
Scene: window seat in a cafe
Outfit: white knitted cardigan + light-colored inner layer
Mood: clean and gentle
Aspect ratio: 9:16
```

The system returns locked parameters, a complete copy-ready prompt, and negative constraints. See [parameter_schema.md](skill/parameter_schema.md) for the full input schema and [usage_examples.md](skill/usage_examples.md) for examples.

## Output Format

```text
1. Locked parameters
2. Style decision
3. Final prompt
4. Negative constraints
5. Optional optimization suggestions
```

## Repository Structure

```text
.
├── README.md
├── README_zh.md
├── README_ja.md
├── README_ko.md
├── SKILL.md
├── agents/openai.yaml
├── skill/
│   ├── skill.md
│   ├── public_instructions.md
│   ├── parameter_schema.md
│   └── usage_examples.md
├── docs/
│   ├── style_guide.md
│   ├── prompt_safety.md
│   ├── versioning.md
│   └── faq.md
└── examples/
```

## Safety Boundaries

This project is intended only for fictional, adult, non-explicit, and non-harmful visual prompt generation. It must not be used for sexualized minors, explicit nudity, non-consensual images, deceptive identity content, harassment, defamation, privacy violations, or other unlawful purposes. See [prompt_safety.md](docs/prompt_safety.md) and [DISCLAIMER.md](DISCLAIMER.md) for details.

## License

This project is licensed under the [MIT License](LICENSE). The MIT License permits use, copying, modification, merging, publishing, distribution, sublicensing, and selling copies. The safety boundaries are responsible-use guidelines and do not alter the standard MIT License terms.

## Author and Version

- Author: Li Yue (李岳)
- Version: `FEMALE-PORTRAIT-DIRECTOR-V1.0`
- Project: `Female Portrait Prompt Director Skill`
