<div align="center">

# 🦁 XXD Shop 007｜产品解构图鉴

### 拆开给你看，每个零件都说得清

<strong>简体中文</strong> · <a href="README.en.md">English</a>

</div>

> 原始提示词：[简体中文原文](references/original-prompt/zh-CN.md) · [English](references/original-prompt/en.md)

## 样张

暂无样张。下文命令只是用法示例，不是视觉证据。

## 它解决什么

数码、家电、个护电器这类产品的详情页，总要有一张“里面有什么”的图。常见的做法要么是工程图，硬得没人看；要么是 AI 随手画一堆发光芯片，好看但都是编的。

**Shop 007** 做的是两者之间的那张图：**高级电商信息图 + 工业设计展示**。产品按真实装配顺序炸开，细线、编号、短标签说清“这是什么部件、解决什么问题”，底部 3–5 个卖点收尾。

关键是**不编**：你给图纸就照图纸拆；术语不明就先查；只有外观图时只拆看得见的部分，内部做克制示意，不给不知道的零件起名字。

## 部件清单从哪来

| 你给了什么 | 怎么拆 |
|---|---|
| 爆炸图、图纸、说明书、部件名单 | 严格照着拆，顺序和名字都按你的 |
| 模块名或原理不清楚 | 先查品牌官方和专业资料，确认后再画 |
| 只有外观图 | 只拆外壳和可见模块，内部做克制示意，不标未知部件 |

整理好的清单和来源写进任务目录的 `facts.md`，画面上每一个标注都能对上。

## 你需要准备

- **产品图：** 外观识别度靠它保留。
- **结构资料：** 越接近“爆炸图 + 部件名单”，拆得越准。
- **参数：** 续航、功率、吸力、像素这类数字用 `--facts` 给，不会凭空出现。

## 快速判断

| 你关心的问题 | 回答 |
|---|---|
| **你会得到什么** | 可直接放进详情页头图、核心卖点页或技术页的产品解构海报 |
| **一眼可辨的特点** | 干净浅底 · 居中爆炸拆分 · 细线编号短标注 · 少量信息卡 · 底部卖点图标 · 少量点缀色高亮 |
| **它不会做什么** | 不杜撰内部结构、不打乱装配顺序、不写说明书式长文 |

## 开始使用

```bash
git clone https://github.com/nevertoday/xxd-shop-007.git
ln -s "$(pwd)/xxd-shop-007" ~/.claude/skills/xxd-shop-007
```

```text
# 有爆炸图和部件名单：严格照资料拆
/xxd-shop-007 ./扫地机外观.png --ref ./官方爆炸图.png=部件顺序与结构 --product "XX 扫地机器人 S8" --facts "部件：上盖、激光雷达、主控板、5200mAh 电池、风机、边刷、主刷、尘盒" --size 3:4 --text prompt --locale zh-CN

# 只有外观图：只拆可见模块
/xxd-shop-007 ./电动牙刷.png --product "声波电动牙刷" --size 3:4 --text prompt --locale zh-CN

# 英文技术页；说明书 PDF 由 Agent 读完整理成部件清单，不会当作参考图送去生图
/xxd-shop-007 ./earbuds.png ./说明书.pdf --product "Wireless earbuds" --size 16:9 --text prompt --locale en-US
```

常用参数：`--product` · `--ref 路径=用途`（图纸、爆炸图；说明书和 PDF 直接附上即可） · `--facts` 参数 · `--size` · `--text prompt / exact / plan` · `--locale`。完整参数见[家族运行合同](references/shop-runtime.md)。

## 边界与信任

- 原始提示词逐字保存，是唯一的审美权威。
- 标注名只来自部件清单；清单的每一行都有来源。
- `--text none` 会让它变成没有标注的纯爆炸渲染，执行前会先告诉你。

<!-- xxd-shop-tail -->
## 项目结构

```text
xxd-shop-007/
├── SKILL.md
├── README.md / README.en.md
├── LICENSE
├── agents/openai.yaml
├── assets/examples/
├── scripts/
│   ├── configured_imagegen.py
│   └── shop_preferences.py
└── references/
    ├── shop-runtime.md
    ├── runtime-preferences.md
    ├── sample-workflow.md
    └── original-prompt/
        ├── README.md
        ├── zh-CN.md
        └── en.md
```

<!-- xxd-readme-ads:start -->
## 关于 XXD

XXD 是小小东品牌名的缩写，本项目由小小东创建并维护：[@xiaoxiaodong01](https://x.com/xiaoxiaodong01)。

## 小小东多端会员 · 699 元/年

> **广告与商业信息声明：** 以下二维码、会员与付费服务链接属于小小东的广告信息。是否扫码或购买完全自愿，不影响本开源项目的访问与使用。

一次年费，同时开通三项会员权益：**知识星球 + 小小东成员提示词库 + 全部 将军总指挥 Skills 会员**。三项权益合并在同一份会员中，无需分别购买。

<!-- xxd-shop-command-system:start -->

### Skills 如何协作

| 层级 | 包含内容 | 用途 |
|---|---|---|
| **General** | `xxd-shop-all` | 识别可用的编号 Skills，按商品、用途和画面需求推荐，并组织多风格试稿与批量任务。 |
| **Soldier** | `xxd-shop-NNN` | 每个编号执行自己的原始提示词与审美，完成 General 分派的具体任务。 |

<!-- xxd-shop-command-system:end -->

### 会员权益

1. **微信一对一 AI 学习与项目答疑**
   扫描下方二维码，添加小小东微信，围绕 AI 学习、工具使用和实际项目进行一对一沟通，获得答疑与建议；代表性问题将整理为会员内容。
2. **持续更新的成员提示词库**
   [小小东成员提示词库](https://vip.xiaoxiaodong.ai/)当前约有 3.2 万条提示词，会持续整理和扩充，目标超过 10 万条。
3. **全部 将军总指挥 Skills 与使用答疑**
   一份会员覆盖全部 将军总指挥 Skills；使用过程中遇到问题，可以获得相应的使用说明与答疑。
4. **高频刚需优先处理**
   会员提出的高频、刚需提示词与 Skills 需求，会优先评估和开发。

### 如何开通

- 可在[成员网站](https://vip.xiaoxiaodong.ai/)自助开通。
- 也可以扫描下方二维码，添加小小东微信，进行一对一沟通并获得开通协助。

<p align="center"><a href="https://xiaoxiaodong.pages.dev/assets/wechat-qr.png"><img src="https://xiaoxiaodong.pages.dev/assets/wechat-qr.png" alt="联系小小东" width="280"></a></p>
<!-- xxd-readme-ads:end -->

## 许可证

本项目（包括 Skill、提示词、脚本、文档及随附样张）采用 **PolyForm Noncommercial License 1.0.0**。完整法律条文请见 [LICENSE](LICENSE)，官方页面见 <https://polyformproject.org/licenses/noncommercial/1.0.0>。

用人话说：

- 个人可以用于学习、研究、实验、测试、兴趣项目和私人娱乐；慈善机构、教育机构、公共研究/安全/卫生机构、环保组织及政府机构也可以使用。
- 在**非商业目的**下，你可以使用、复制、修改、制作衍生作品并分享；分享时必须同时提供本许可证（或上面的链接）以及作者提供的所有 `Required Notice:` 声明。
- 不允许用于商业产品或服务、收费交付、出售访问权或许可，或任何预期会带来商业应用的用途。需要商业使用时，请先向版权方另行取得书面许可。
- 本协议只授予其中明确写出的著作权许可和有限的专利许可，不授予商标、品牌名称或其他未明确授予的权利，也不能把你的许可再转授给他人。
- 如果收到书面违约通知，须在 32 天内纠正并采取实际补救措施，否则许可会立即终止；就专利侵权提出书面主张也会终止专利许可。
- 内容按“现状”提供，在法律允许的范围内不作任何担保，使用风险和可能的损失由使用者自行承担。
