<div align="center">

**中文** · [English](./README.md)

# 🎨 Design Style Skill

---

**从 67 种精选视觉美学里挑一款，直接落到项目代码里 — 只要 3 步。**

[![License](https://img.shields.io/badge/LICENSE-MIT-4c8bf5?style=flat-square&labelColor=333)](./LICENSE)
[![Version](https://img.shields.io/badge/VERSION-1.0.0-2ea44f?style=flat-square&labelColor=333)]()
[![Stars](https://img.shields.io/github/stars/yanliudesign/design-style-skill?style=flat-square&label=STARS&color=e37f2c&labelColor=333)](https://github.com/yanliudesign/design-style-skill/stargazers)

[![Claude Code](https://img.shields.io/badge/Claude_Code-Skill-d97757?style=flat-square&labelColor=1a1a1a&logo=anthropic&logoColor=white)](https://claude.ai/code)
[![Codex](https://img.shields.io/badge/Codex-Skill-2ea44f?style=flat-square&labelColor=1a1a1a)]()
[![OpenCode](https://img.shields.io/badge/OpenCode-Skill-4c8bf5?style=flat-square&labelColor=1a1a1a)]()
[![OpenClaw](https://img.shields.io/badge/OpenClaw-Skill-8b5cf6?style=flat-square&labelColor=1a1a1a)]()
[![Hermes](https://img.shields.io/badge/Hermes-Skill-e879a8?style=flat-square&labelColor=1a1a1a)]()

</div>

> 🧪 交互式实验室：**[design-lab-yanliu.vercel.app](https://design-lab-yanliu.vercel.app/)** — 一次性浏览全部 **67 种风格**，颜色、CSS、Prompt 模板一键复制。

一个专门挑设计风格的 agent skill。告诉它你在做什么、想要什么感觉，它一次给你 **3 个立场明确的推荐** —— 每一个都配真实的配色、可粘贴的 CSS 变量、字体建议、prompt 模板。选一个之后，它会把这套视觉直接融进你现有的代码（Tailwind / vanilla CSS / styled-components / 纯 HTML 都行）。不是灵感板、不是 15 个模糊选项 —— 是 3 个今天就能上线的具体方案。

---

## 整个 skill 只有 3 步

用任何模糊的话都能触发（"帮我选设计风格" / "apply glassmorphism 到我的落地页" / "推荐设计风格"），流程都一样：

1. **告诉我项目 + Vibe** — 一个问题问你在做什么（SaaS / 作品集 / 电商 / 博客 / 落地页），一个问题问要什么感觉（专业稳重 / 大胆前沿 / 温暖亲切 / 极简克制）。如果你第一句话里两个都说了，这步就跳过。
2. **拿到 3 个风格推荐** — 每个都配：一句话"为什么是它"、4 色调色板、DNA 分数（圆润度 / 对比度 / 温度），以及"为什么它比另外两个更适合你"的 2 句解释。
3. **落到你的代码里** — 选一个，skill 会扫描你现有项目（用了 Tailwind config？CSS 变量？styled-components？），然后**用你项目自己的写法**注入配色/字体/圆角/阴影，同时给你 Google Fonts / Fontshare 的 `<link>`、以及一个示例组件（卡片/按钮/导航）让你立刻看到效果。

三个侧边入口：

- **查询模式** — "介绍下 glassmorphism" → 跳过前面直接进 Phase 3，展示完整风格卡。
- **仅应用模式** — "把 cyberpunk 应用到这个文件" → 跳过推荐直接进 Phase 4。
- **直接命名** — 任何 query 里点名一个风格，都当作已选风格处理。

---

## 67 种风格一览

按创新度分层，按项目类型匹配。下面只是取样 —— 完整库在 [`styles-reference.md`](./styles-reference.md)，可交互版本在 **[design-lab-yanliu.vercel.app](https://design-lab-yanliu.vercel.app/)**。

| 层级 | Vibe | 代表风格 |
|-----|------|---------|
| **1 · 保守** | 专业、可信、企业安全区 | Corporate Clean · Japandi · Minimalist · Editorial Serif · Swiss Grid |
| **2 · 现代** | 干净、当代、大多数 SaaS 的默认盘 | Glassmorphism · Neumorphism · Nordic · Material 3 · Soft UI |
| **3 · 有辨识度** | 有立场、有记忆点、够 signature | Brutalism · Bento Grid · Terminal · Y2K Aero · Editorial Magazine |
| **4 · 实验性** | 大胆、冒险、作品集级 | Cyberpunk · Vaporwave · Memphis · Anti-Design · Glitchcore |

每个风格条目都包含：完整调色板（7+ token 带角色）、可复制的 CSS snippet、3 种 prompt 模板（Basic / Advanced / Keywords）、Do's & Don'ts、DNA 分数、3 个相关风格。

---

## 四条原则

1. **只给答案，不讲道理** — 直接给具体 CSS、颜色、prompt 模板。不讲理论、不讲历史、不讲"什么是设计"。
2. **上下文优先** — 金融 dashboard 需要的风格 ≠ 独立游戏落地页需要的风格。推荐永远绑定**你**的项目。
3. **有立场** — 永远 3 个，不给 15 个。解释**为什么是这 3 个适合你的具体场景**，不是"这里有一些选项"。
4. **能立刻用** — 每一个输出都是 CSS 变量、prompt 字符串、可以直接粘的代码。不留"你还可以继续探索"这种课后作业。

---

## 文件结构

```
design-style-skill/
├── SKILL.md                # 入口 · 4 个 Phase（识别模式 / 理解项目 / 展示风格 / 应用到代码）
├── styles-reference.md     # 67 种风格库 — 颜色 / CSS / prompt / DNA 分数
└── README.md               # 你正在读的这份
```

配套的交互实验室（真正可以点开看的可视化版本）在 **[design-lab-yanliu.vercel.app](https://design-lab-yanliu.vercel.app/)** —— 那才是风格库的 source of truth。

---

## 设计思路

- **风格是意图的捷径** — 选 Glassmorphism 还是 Brutalism 不是化妆题，而是在声明你是谁、看重什么、想排除谁。这个 skill 把风格选择当**定位决策**，不是**装饰决策**。
- **3 是正确的数字** — 1 个太独裁，15 个决策瘫痪。3 个能对比，但也**逼**你为偏好辩护。
- **DNA 分数 > 标签** — "Glassmorphism" 是标签，*圆润度 3 / 对比度 2 / 温度 2* 是坐标。有了坐标，就算标签听起来完全不同，你也能在共享 DNA 的风格之间切换。
- **应用 > 描述** — 风格只有进到 codebase 里才有用。skill 真正交付的是"你的项目开始**看起来像**那种风格"的那一刻，不是一段关于那种风格的介绍。

---

## 相关链接

- 🧪 **[design-lab-yanliu.vercel.app](https://design-lab-yanliu.vercel.app/)** — 交互式 67 风格实验室（颜色、prompt、一键复制）
- 📚 [`styles-reference.md`](./styles-reference.md) — 整个库的单文件 Markdown 版
- 🧠 [`SKILL.md`](./SKILL.md) — skill 的路由、Phase、guardrails

---

## License

MIT 协议 — 随便 fork、改造、发一个你自己的版本。

Created by [Dreameryanyan](https://www.linkedin.com/in/yanliudesign/) · [LinkedIn](https://www.linkedin.com/in/yanliudesign/) · [X](https://x.com/yanliudreamer) · [小红书](https://www.xiaohongshu.com/notification)
