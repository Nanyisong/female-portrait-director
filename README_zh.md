[English](README.md) | [简体中文](README_zh.md) | [日本語](README_ja.md) | [한국어](README_ko.md)

# 女性人像提示词导演 Skill

女性人像提示词导演 Skill 是一个面向 AI 生图场景的结构化女性人像提示词生成系统，支持清纯生活照、纯欲曲线生活照、都市时尚写真、古风仙侠美人图、电商服装模特图等多种风格。系统内置参数锁定、风格路由、五官模块、身形模块、镜头光线补全和负面约束优化机制，帮助用户用简单参数生成稳定、合规、可复制的 AI 图像提示词。

本项目不是普通提示词合集，而是一个可扩展的女性人像提示词 Skill 框架。

## 项目定位

通过少量输入参数生成完整提示词，并在保留用户明确要求的前提下自动补全五官、身形、镜头、光线、滤镜、平台用途和负面约束。默认人物必须是明确成年的女性，输出强调真实摄影质感、克制表达和稳定生成。

## 支持风格

- 清纯生活照
- 纯欲曲线生活照
- 都市时尚写真
- 古风仙侠美人图
- 电商服装模特图

## 核心能力

- 锁定用户已经填写的参数，只做细化和稳定化补全。
- 根据目标风格调用对应母版，避免互相冲突的风格词堆叠。
- 自动补全五官差异化、身形、镜头、光线、滤镜和负面约束。
- 支持提示词生成、已有提示词优化、失败诊断、参数组合推荐和审查友好改写。
- 为电商图片保留服装展示优先级，为曲线风格保留明确的安全边界。

## 快速开始

将仓库作为 Codex Skill 使用时，可直接调用 `$female-portrait-director`。最简输入示例：

```text
风格：清纯生活照
场景：咖啡馆靠窗座位
服装：白色针织开衫 + 浅色内搭
气质：清纯温柔
画幅：9:16
```

系统将输出参数锁定结果、可直接复制的完整提示词和负面约束。完整调用字段参见 [parameter_schema.md](skill/parameter_schema.md)，示例参见 [usage_examples.md](skill/usage_examples.md)。

## 输出格式

```text
一、参数锁定结果
二、风格判断
三、最终提示词
四、负面约束
五、可选优化建议
```

## 文件结构

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

## 安全边界

本项目仅用于虚构、成年、非裸露、非伤害性的视觉提示词生成。禁止用于未成年人性化、色情裸露、非自愿图像、欺骗性身份内容、骚扰、诽谤、隐私侵犯或其他违法违规用途。详细规则参见 [prompt_safety.md](docs/prompt_safety.md) 和 [DISCLAIMER.md](DISCLAIMER.md)。

## License

本项目使用 [MIT License](LICENSE)。MIT License 允许使用、复制、修改、合并、发布、分发、再许可和销售副本。安全边界属于合理使用说明，不改变 MIT License 的标准授权范围。

## 作者与版本

- 作者：李岳
- 版本：`FEMALE-PORTRAIT-DIRECTOR-V1.0`
- 项目：`Female Portrait Prompt Director Skill`
