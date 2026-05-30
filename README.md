[English](README.md) | [简体中文](README_zh.md) | [日本語](README_ja.md) | [한국어](README_ko.md)

# Female Portrait Prompt Director Skill

Female Portrait Prompt Director Skill is a structured prompt-generation and visual-direction system for AI image creation. It supports clean lifestyle portraits, restrained curve-focused lifestyle portraits, urban fashion photography, gufeng fantasy portraits, and e-commerce clothing model images. V1.3 locks explicit parameters, fully expands age cues, facial features, body, pose, outfit, scene, camera, lighting, and filter controls, then fuses them into a coherent photographed moment.

This project is not a generic prompt collection. It is an extensible female portrait prompt Skill framework.

## Project Scope

Generate complete prompts from a small set of input parameters. Preserve the user's explicit requirements while visually expanding facial features, body shape, outfit, scene, camera and pose, lighting, filters, platform purpose, and negative constraints. Subjects must be clearly adult women. Outputs emphasize realistic photography, restrained expression, visual coherence, and stable generation.

## Supported Styles

- Clean lifestyle portraits
- Restrained curve-focused lifestyle portraits
- Urban fashion photography
- Gufeng fantasy portraits
- E-commerce clothing model images

## Core Capabilities

- Lock user-specified parameters and only refine or stabilize them.
- Route each request through one on-demand style file and avoid conflicting style keywords.
- Parse face, body, outfit, scene, camera and pose, lighting, and filter modules.
- Expand short parameters into a coherent photographed moment instead of mechanically repeating them.
- Fuse the expanded modules into natural, detailed, copy-ready prompts with photography-director intent.
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

## Installation

Clone the repository into your Codex skills directory.

Windows PowerShell:

```powershell
git clone https://github.com/liyue-aigc/female-portrait-director.git "$env:USERPROFILE\.codex\skills\female-portrait-director"
```

macOS or Linux:

```bash
git clone https://github.com/liyue-aigc/female-portrait-director.git "${CODEX_HOME:-$HOME/.codex}/skills/female-portrait-director"
```

Start a new Codex conversation, then invoke:

```text
$female-portrait-director
```

## Example: Parameters to Directed Prompt

The Skill does more than restate the input. It preserves requested parameters, fills in missing visual details, and produces locked parameters, module analysis, a final prompt, and negative constraints.

```text
Portrait style: Gufeng xianxia beauty portrait
Scene: Traditional courtyard corridor surrounded by misty mountains and water
Outfit: Moon-white Tang-inspired fantasy wide-sleeve robe + flowing pibo scarf + silver embroidered waist sash
Mood: Cool, distant, ethereal
Facial direction: Classical East Asian beauty
Body direction: Slender and delicate figure
Camera direction: Slight side-facing standing pose, half-body to thigh framing
Lighting: Cool soft light
Filter: Cool ethereal gufeng filter
Aspect ratio: 9:16
Platform use: Character portrait
```

![Gufeng xianxia prompt expansion example](assets/examples/gufeng-director-output.jpg)

## Output Format

```text
1. Locked parameters
2. Module analysis
3. Final prompt
4. Negative constraints
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
├── assets/examples/
├── skill/
│   ├── skill.md
│   ├── public_instructions.md
│   ├── parameter_schema.md
│   ├── usage_examples.md
│   ├── references/
│   │   ├── director-expansion.md
│   │   └── visual-libraries.md
│   └── routes/
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
- Version: `FEMALE-PORTRAIT-DIRECTOR-V1.3`
- Project: `Female Portrait Prompt Director Skill`
