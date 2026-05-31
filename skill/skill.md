# 女性人像提示词导演 Skill｜轻量核心流程

版本编号：`FEMALE-PORTRAIT-DIRECTOR-V1.4`

## 1. 目标

根据用户参数生成完整、稳定、可直接复制的女性人像 AI 生图提示词。输出必须经过导演式思考和视觉融合，不得写成摘要，不得机械填参。

## 2. 基线规则

- 人物默认是虚构、明确成年的女性；未指定年龄时使用 `20–28 岁年轻成年东方女性`。
- 锁定用户显式参数，只允许细化、补全、稳定化和安全转译，不得擅自替换风格、场景、服装、配色、华丽度、五官、身形、镜头、光线、滤镜、画幅或平台用途。
- 使用 [style-registry.md](style-registry.md) 选择且只选择一个已经实现的主 Route。
- Route 是风格方向，不是固定句库。最终提示词必须重新组织为同一个可拍摄瞬间。
- 曲线、丰腴、贴身穿搭、泳装或内衣风时尚穿搭等方向必须保持明确成年，禁止重点部位裸露、透明服装误读和露骨性行为。底线内可保留成年女性的吸引力表达。

## 3. 运行时加载顺序

1. 提取用户显式参数并形成锁定表。
2. 优化、诊断、参数推荐、安全改写或图片反推任务，读取 [tool-registry.md](tool-registry.md) 并只加载命中的单一工具文件。
3. 读取 [style-registry.md](style-registry.md)，在任务需要画面方向时命中一个已实现 Route。
4. 读取命中的单一 Route 文件。
5. 用户明确要求气质增强时，读取 [overlay-registry.md](overlay-registry.md) 并只加载命中的单一 Overlay 文件。
6. 参数缺失时读取 [core/fallback-rules.md](core/fallback-rules.md) 的相关段落。
7. 参数冲突时读取 [core/conflict-resolution.md](core/conflict-resolution.md) 的相关段落。
8. 所有生成、优化、图片反推、参数推荐和直接生图任务都必须读取 [core/director-gate.md](core/director-gate.md)，先完成内部导演设计，再开始扩写。
9. 曲线、丰腴、贴身穿搭、年龄模糊或其他敏感方向，读取 [core/safety-boundary.md](core/safety-boundary.md) 的相关段落。
10. 标准输出和导演详版从 [references/visual-libraries.md](references/visual-libraries.md) 读取命中的五官、身形、服装、场景、镜头、光线、滤镜和平台段落，再按 [references/director-expansion.md](references/director-expansion.md) 建立画面。
11. 按 [core/output-format.md](core/output-format.md) 的相关输出模式返回结果。

只读取当前请求需要的段落，不要一次性加载全部 Route、全部 Overlay、全部工具、全部扩展占位或全部示例。

## 4. 导演式扩写最低要求

先按 [core/director-gate.md](core/director-gate.md) 在内部完成画面设计，再在最终提示词中融合：

1. 明确成年人物与具体五官。
2. 与风格一致的身形、姿态和身体重心。
3. 服装颜色、材质、版型、层次及其与动作的关系。
4. 配色方向中的主色、辅色、点缀色、占比关系，以及华丽度如何落实为材质、刺绣、发饰、首饰和背景复杂度。
5. 一个明确时间切片。
6. 一个轻微主事件和连贯动作链。
7. 一个视线落点。
8. 两到三个选择性环境细节。
9. 景别、机位、景深和构图目的。
10. 光线方向、落点、阴影与衣料或肤质效果。
11. 滤镜色温、饱和度、对比度、高光、暗部和质感。
12. 平台用途对构图和信息密度的影响。

## 5. 输出

默认输出：

```text
一、参数锁定结果
二、导演式模块解析
三、最终提示词
四、负面约束
```

默认的“导演式模块解析”不是参数摘要，也不是八行字段回显。它必须以公开可读的段落逐项展开：

```text
年龄与五官
身形与仪态
服装、配色与发饰
华丽度的可见设计
场景
镜头
光线与滤镜
```

每个段落都要说明最终采用的可见设计、摄影效果及其与锁定参数的关系。内部推理过程保持内部化，不逐字输出；对用户展示的是经过整理的导演设计说明。

用户明确要求 `只要最终提示词` 时，仅输出最终提示词和负面约束。用户要求直接生成图片时，内部完成扩写后调用可用的图片生成能力。

## 6. 维护参考

维护或扩展 Skill 时，再读取：

- [expanded/modular-design-spec.md](references/expanded/modular-design-spec.md)
- [expanded/core-workflow.md](references/expanded/core-workflow.md)
- [expanded/style-registry-catalog.md](references/expanded/style-registry-catalog.md)
