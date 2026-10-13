---
name: xxd-shop-007
description: "Create XXD Shop 007 exploded product teardown info posters (产品解构信息海报 / 零部件拆分图) as finished PNGs from product photos, drawings, exploded views, manuals, structure diagrams or descriptions, treating the bundled original brief as the sole aesthetic authority: a clean modern industrial-design infographic with the product exploded along its real assembly order, thin leader lines, numbered short labels saying what each part is and what problem it solves, optional insight cards, and 3–5 benefit icons — never inventing internals the sources do not show. Supports multiple ratios or exact sizes, prompt-generated, user-exact or user-plan labels. Also plans a detail-page set (--set): an overall teardown, a key-module page and a technical cutaway, each labelling only its share of the parts list. Use when the user invokes xxd-shop-007 or asks for 爆炸图、产品拆解图、结构解析图、零部件图、详情页技术页、产品解构图鉴、拆解详情组."
---

# XXD Shop 007｜产品解构图鉴

用本次的产品图、图纸、爆炸图、说明书、结构示意或文字说明，生成一张电商用途的产品解构信息海报，交付 PNG。

每次生成前，完整读取 `references/original-prompt/zh-CN.md`。这份中文原始提示词是唯一的创作与审美权威；不总结、不翻译、不混用，也不用本文件、README、样张或其他编号替代它。

每次构建生图请求前，完整读取 `references/shop-runtime.md`，它是唯一的家族运行合同。本 Skill 不另写第二套美术指导或运行规则。

所有成品直接写进 `~/Desktop/xxd/xxd-shop-007/` 下新建的一个任务目录（或 `--out` 指定的根目录），不建子目录，不自动拼总览。

## 本编号覆盖条款

**部件清单是这张图的骨架，生成前由 Agent 整理。** 原稿要求“先准确识别产品类型、外观结构、核心组件、内部模块、装配逻辑……”，并且不许凭空编造内部组件。来源按优先级：

1. 用户提供的图纸、爆炸图、说明书、部件名称、拆解顺序或模块说明：严格遵循。
2. 用户提供的术语、模块名或原理不明确时，按原稿要求查证：品牌官方、说明书、专业资料、公开可信来源。
3. 只有外观图、没有内部资料时：只拆外壳和看得见的模块，内部做原稿所说的“合理、克制的示意化拆分”，不画芯片级细节，不给未经证实的内部部件起名字。

把清单写进任务目录的 `facts.md`：

```text
| 序号 | 部件 | 层级／装配顺序 | 功能（一句话） | 来源 |
|---|---|---|---|---|
```

说明书、PDF、规格表这类文字资料由 Agent 阅读后整理进清单，不当作参考图送进生图；只有图纸、爆炸图、结构示意这类图像，才按 `--ref` 的用途作为参考图交给图像模型。

清单按装配顺序写进本次商品块的“可用事实”，标题为“部件清单（按装配顺序）”。内部不明时，另写一行“内部结构未提供：只做克制示意，不标未知部件名”。

**标注与卖点都来自清单。** 每个标注的部件名必须在清单里；原稿底部的 3–5 个核心卖点，只来自清单功能、用户卖点和已核实的资料。参数、续航、吸力、像素等数字只来自“可用事实”（`--facts`、用户资料、已核实来源）。

**“不要文字”会失去信息图。** 原稿的核心是“细线引导、编号、简洁标签”。`--text none` 时说明冲突：成品会变成没有标注的纯爆炸渲染。用户确认后照做。

**版式语言：** 原稿顶部栏目标题举例“产品解构图鉴”，按文字语言自然转写；英文时用对应英文，不保留中文。

**套图：拆解详情组（启用）。** 原稿写明它适用于“电商详情页头图、核心卖点页、产品技术页”，一组详情图就是这几种页各出一张。按家族“套图”一节执行，本编号的约定：

- **默认张数：** 3。用户可以用 `--set N` 改成 2–5 张。
- **套图角色：** 头图（整机拆解，看清整体与装配关系）、核心卖点页（一个关键模块及它解决的问题）、产品技术页（局部剖开，加原稿列出的一种信息卡：工作原理、技术亮点、气流路径、光学路径、避障逻辑或传感器作用）。张数多于 3 时，增加的是更多模块页或技术页。
- **部件清单按张分配：** 头图标注清单里的主要部件；每张模块页和技术页只标它那个模块在清单里的部件。任何一张都不出现清单外的部件名。原稿底部的 3–5 个核心卖点只放在头图上，不在每张重复。
- **材料不够就少做：** 内部结构没有资料时，只做头图和外壳或可见模块页，告诉用户为什么少了；不为凑张数虚构内部模块。
- **继承项：** 背景色，产品渲染质感，线条、箭头、编号与图标的统一风格，强调色的用法。
- **构图来源：** 原稿列出的拆分方向，包括纵向分层拆解、前后展开、左右拆分、模块悬浮展开和局部剖开显示。相邻两张不用同一种。
- **标题：** 原稿规定主标题是产品名称，所以每张的主标题都是产品名称；各张靠副标题区分，副标题按原稿“说明品类与解构主题”写本张的解构主题。
- **追加验收：** 每张都只标清单里分给它的部件；模块页和技术页看得出是从头图那台产品里拆出来的；线条、编号与图标的风格整组一致。

**追加验收：** 拆分方向与装配逻辑一致，部件顺序与清单一致；没有清单外的标注名；产品外观识别度保留；线条、箭头、编号、图标风格统一；第一眼先看到整体与拆分关系，局部信息卡没有压过主体。

**写入提示词：** 以下句子原话放进交付块的“本编号约束”；其余覆盖条款由 Agent 执行与验收，不进入提示词。

- 每个标注的部件名都来自“可用事实”里的部件清单，不标清单以外的部件。
- 主标题是产品名称；副标题说明品类与本张的解构主题。做套图时，底部 3–5 个核心卖点只放在头图，其他张不重复。
- 底部 3–5 个核心卖点只来自用户卖点、部件清单里写的功能和“可用事实”；不另写安全保护、认证、材质等级这类没有提供的说法。

## 参考文件

- `references/shop-runtime.md`：家族运行合同（含事实纪律与 `facts.md`）
- `references/original-prompt/zh-CN.md`：运行时使用的原始提示词
- `references/original-prompt/README.md`：译文索引与权威说明
- `references/runtime-preferences.md`：交付偏好沿用
- `references/sample-workflow.md`：仅用于维护样张
- `scripts/configured_imagegen.py`、`scripts/shop_preferences.py`
