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

完整库 —— 每个风格都配有：调色板、DNA 分数、prompt 模板、CSS 代码片段、Do's & Don'ts。想看完整 spec 请跳到 [`styles-reference.md`](./styles-reference.md)。可交互版本：**[design-lab-yanliu.vercel.app](https://design-lab-yanliu.vercel.app/)**。

**Tag 说明：** `Easy` `Medium` `Advanced`（难度）· `Light` `Dark` `Bold`（调性）· `🔥 Trend`（当下正热）

<!-- Gallery: all 67 styles. Each row = preview + name + description + tags + palette. -->
<table>
<tr>
<td width="260"><img src="previews/brutalism.png" width="240" alt="Brutalism"></td>
<td>

<strong>01. 粗野主义</strong> · <em>Brutalism</em><br>
<sub>Easy · Light</sub>

粗犷、大胆，粗黑边框 + 高对比 + 硬边阴影。作品集、创意工作室的最爱。

`#000000` `#FFFFFF` `#FF3B00` `#FFDE59`

</td>
</tr>
<tr>
<td width="260"><img src="previews/glass.png" width="240" alt="Glassmorphism"></td>
<td>

<strong>02. 玻璃拟态</strong> · <em>Glassmorphism</em><br>
<sub>Medium · Light · 🔥 Trend</sub>

磨砂玻璃感，透明模糊 + 彩色背景上的半透明面板，制造层次与纵深。

`#667eea` `#764ba2` `#f093fb` `#ffffff26`

</td>
</tr>
<tr>
<td width="260"><img src="previews/neo.png" width="240" alt="Neomorphism"></td>
<td>

<strong>03. 新拟态</strong> · <em>Neomorphism</em><br>
<sub>Easy · Light</sub>

柔和 3D 感，同色背景上的双向阴影，触觉化界面。

`#E4E9F0` `#BEC8D4` `#FFFFFF` `#667eea`

</td>
</tr>
<tr>
<td width="260"><img src="previews/minimal.png" width="240" alt="Minimalism"></td>
<td>

<strong>04. 极简主义</strong> · <em>Minimalism</em><br>
<sub>Medium · Light</sub>

大量留白 + 精心排版，克制即高级，专业感与信任感。

`#FAFAFA` `#1A1A1A` `#999999` `#E0E0E0`

</td>
</tr>
<tr>
<td width="260"><img src="previews/y2k.png" width="240" alt="Retro"></td>
<td>

<strong>05. Y2K / 千禧风</strong> · <em>Retro</em><br>
<sub>Advanced · Light · 🔥 Trend</sub>

千禧年怀旧色，粉+青+紫的糖果色，Gen Z / 潮牌电商大爱。

`#FF6B9D` `#C66AFF` `#00D4FF` `#FFFFFF`

</td>
</tr>
<tr>
<td width="260"><img src="previews/luxury.png" width="240" alt="Dark Luxury"></td>
<td>

<strong>06. 暗黑奢华</strong> · <em>Dark Luxury</em><br>
<sub>Medium · Dark</sub>

暗黑奢华，黑金配色 + 衬线大字，珠宝腕表 / 私人银行专用。

`#0A0A0A` `#C5A55A` `#F5E6C8` `#1A1A1A`

</td>
</tr>
<tr>
<td width="260"><img src="previews/organic.png" width="240" alt="Organic"></td>
<td>

<strong>07. Nature / 有机自然</strong> · <em>Organic</em><br>
<sub>Medium · Light</sub>

有机自然色，暖米/苔绿/木色，Wellness / 生活方式产品首选。

`#F4EDE4` `#6B8F71` `#D4A574` `#3D5A3E`

</td>
</tr>
<tr>
<td width="260"><img src="previews/cyber.png" width="240" alt="Cyberpunk"></td>
<td>

<strong>08. 赛博朋克</strong> · <em>Cyberpunk</em><br>
<sub>Advanced · Dark · 🔥 Trend</sub>

赛博朋克，深紫底 + 荧光粉青双色，霓虹发光，未来感十足。

`#0D0221` `#FF2E97` `#00FFF0` `#1A0533`

</td>
</tr>
<tr>
<td width="260"><img src="previews/clay.png" width="240" alt="Claymorphism"></td>
<td>

<strong>09. 粘土风</strong> · <em>Claymorphism</em><br>
<sub>Easy · Light · 🔥 Trend</sub>

粘土 3D 质感，圆润饱和，玩具/儿童产品友善又可爱。

`#F0F0F3` `#7C5CFC` `#FF6B8A` `#FFB347`

</td>
</tr>
<tr>
<td width="260"><img src="previews/editorial.png" width="240" alt="Editorial"></td>
<td>

<strong>10. 编辑排版风</strong> · <em>Editorial</em><br>
<sub>Advanced · Light</sub>

杂志编辑排版，粗衬线 + 网格，最能展示设计品味。

`#FFFDF8` `#1A1A1A` `#E63946` `#999999`

</td>
</tr>
<tr>
<td width="260"><img src="previews/flat.png" width="240" alt="Flat Design"></td>
<td>

<strong>11. 扁平设计</strong> · <em>Flat Design</em><br>
<sub>Easy · Light</sub>

扁平设计，纯色 + 明确层级，学习成本最低。

`#FFFFFF` `#4285F4` `#E8E8E8` `#212121`

</td>
</tr>
<tr>
<td width="260"><img src="previews/material.png" width="240" alt="Material Design"></td>
<td>

<strong>12. 材质设计</strong> · <em>Material Design</em><br>
<sub>Easy · Light</sub>

Google Material，成熟组件库，SaaS/工具的稳妥选择。

`#FFFFFF` `#6200EA` `#B388FF` `#F0F0F0`

</td>
</tr>
<tr>
<td width="260"><img src="previews/swiss.png" width="240" alt="Swiss Minimalist"></td>
<td>

<strong>13. 瑞士极简</strong> · <em>Swiss Minimalist</em><br>
<sub>Medium · Light</sub>

瑞士极简，网格 + Helvetica，理性、克制、经典。

`#FFFFFF` `#1A1A1A` `#E63946` `#E0E0E0`

</td>
</tr>
<tr>
<td width="260"><img src="previews/vapor.png" width="240" alt="Vaporwave"></td>
<td>

<strong>14. 蒸汽波</strong> · <em>Vaporwave</em><br>
<sub>Advanced · Dark · 🔥 Trend</sub>

蒸汽波，紫粉蓝渐变 + 电子迷幻，数字艺术/独立音乐。

`#1a0030` `#FF71CE` `#01CDFE` `#B967FF`

</td>
</tr>
<tr>
<td width="260"><img src="previews/artdeco.png" width="240" alt="Art Deco"></td>
<td>

<strong>15. 装饰艺术</strong> · <em>Art Deco</em><br>
<sub>Advanced · Dark</sub>

Art Deco 装饰艺术，黑金几何 + 对称衬线，高奢品牌感。

`#1A2332` `#D4AF37` `#F0E6D0` `#E8DCC8`

</td>
</tr>
<tr>
<td width="260"><img src="previews/bauhaus.png" width="240" alt="Bauhaus"></td>
<td>

<strong>16. 包豪斯</strong> · <em>Bauhaus</em><br>
<sub>Medium · Light</sub>

包豪斯，红黄蓝三原色 + 几何构成，功能主义美学。

`#F5F0E8` `#E63946` `#2D5FD8` `#FFD43B`

</td>
</tr>
<tr>
<td width="260"><img src="previews/terminal.png" width="240" alt="Terminal"></td>
<td>

<strong>17. 终端风</strong> · <em>Terminal</em><br>
<sub>Easy · Dark</sub>

终端命令行，等宽字体 + 绿字黑底，Geek / Dev 工具灵魂。

`#0C0C0C` `#00FF41` `#333333` `#888888`

</td>
</tr>
<tr>
<td width="260"><img src="previews/mono.png" width="240" alt="Monochrome"></td>
<td>

<strong>18. 单色风</strong> · <em>Monochrome</em><br>
<sub>Easy · Dark</sub>

纯黑白单色，克制到极致，摄影/设计作品集的经典底座。

`#000000` `#FFFFFF` `#888888` `#333333`

</td>
</tr>
<tr>
<td width="260"><img src="previews/boldtype.png" width="240" alt="Bold Typography"></td>
<td>

<strong>19. 粗体排版</strong> · <em>Bold Typography</em><br>
<sub>Medium · Light</sub>

超大粗体排版，字就是设计，Editorial 或个人品牌用。

`#F2F0ED` `#111111` `#FF4D2E` `#666666`

</td>
</tr>
<tr>
<td width="260"><img src="previews/web3.png" width="240" alt="Web3"></td>
<td>

<strong>20. Web3 风</strong> · <em>Web3</em><br>
<sub>Medium · Dark · 🔥 Trend</sub>

Web3 未来感，深色底 + 紫蓝渐变 + 荧光点缀，Crypto/AI 产品首选。

`#0A0A1A` `#6366F1` `#A78BFA` `#EC4899`

</td>
</tr>
<tr>
<td width="260"><img src="previews/industrial.png" width="240" alt="Industrial"></td>
<td>

<strong>21. 工业风</strong> · <em>Industrial</em><br>
<sub>Medium · Dark</sub>

工业风，金属灰 + 橙色警示，制造/工程/硬件类产品。

`#2A2A28` `#F5A623` `#C8C4B8` `#4A4A45`

</td>
</tr>
<tr>
<td width="260"><img src="previews/academia.png" width="240" alt="Academia"></td>
<td>

<strong>22. 学术风</strong> · <em>Academia</em><br>
<sub>Easy · Light</sub>

学术风，米黄底 + 衬线 + 深棕，教育/研究/深度内容站点。

`#F5F1E8` `#3A3428` `#8B7D65` `#D4C9B0`

</td>
</tr>
<tr>
<td width="260"><img src="previews/saas.png" width="240" alt="SaaS"></td>
<td>

<strong>23. SaaS 风格</strong> · <em>SaaS</em><br>
<sub>Easy · Light · 🔥 Trend</sub>

SaaS 标准，蓝紫强调色 + 干净布局，转化率与信任的最优解。

`#F8FAFC` `#3B82F6` `#6366F1` `#94A3B8`

</td>
</tr>
<tr>
<td width="260"><img src="previews/news.png" width="240" alt="Newsprint"></td>
<td>

<strong>24. 报纸风</strong> · <em>Newsprint</em><br>
<sub>Medium · Light</sub>

报纸风，米色纸感 + 衬线 + 密排文本，新闻/长文类。

`#F0EBDD` `#1A1A1A` `#444444` `#888888`

</td>
</tr>
<tr>
<td width="260"><img src="previews/maximal.png" width="240" alt="Maximalism"></td>
<td>

<strong>25. 极繁主义</strong> · <em>Maximalism</em><br>
<sub>Advanced · Light · 🔥 Trend</sub>

极繁主义，色彩爆炸 + 混合排版，创意工作室大胆之作。

`#FF6B6B` `#FFE66D` `#4ECDC4` `#A78BFA`

</td>
</tr>
<tr>
<td width="260"><img src="previews/sketch.png" width="240" alt="Sketch"></td>
<td>

<strong>26. 手绘风</strong> · <em>Sketch</em><br>
<sub>Medium · Light</sub>

手绘风，铅笔线条 + 温暖米色，个人博客/儿童产品充满人味。

`#FEFCF8` `#333333` `#FF7E5F` `#E0DDD5`

</td>
</tr>
<tr>
<td width="260"><img src="previews/botanical.png" width="240" alt="Botanical"></td>
<td>

<strong>27. 植物风</strong> · <em>Botanical</em><br>
<sub>Medium · Light</sub>

植物风，绿+米色 + 手绘叶片，Wellness/生活方式必备。

`#F7F3EE` `#6B8F4E` `#2E3D20` `#D5CDB8`

</td>
</tr>
<tr>
<td width="260"><img src="previews/moddark.png" width="240" alt="Modern Dark"></td>
<td>

<strong>28. 现代暗色</strong> · <em>Modern Dark</em><br>
<sub>Easy · Dark · 🔥 Trend</sub>

现代暗色，深灰底 + 蓝色强调 + 精致细节，Dev/Trading 标配。

`#111113` `#18181B` `#3B82F6` `#71717A`

</td>
</tr>
<tr>
<td width="260"><img src="previews/geo.png" width="240" alt="Playful Geometric"></td>
<td>

<strong>29. 几何趣味</strong> · <em>Playful Geometric</em><br>
<sub>Medium · Light</sub>

几何趣味，明快色块 + 圆润形状，儿童/教育/娱乐产品。

`#FFF5F5` `#FF6B6B` `#FFE66D` `#388E3C`

</td>
</tr>
<tr>
<td width="260"><img src="previews/kinetic.png" width="240" alt="Kinetic"></td>
<td>

<strong>30. 动感风</strong> · <em>Kinetic</em><br>
<sub>Medium · Dark</sub>

动感风，动效驱动的视觉，速度与激情，运动/游戏类。

`#0F0F14` `#FF4D4D` `#FF8C00` `#E0E0E0`

</td>
</tr>
<tr>
<td width="260"><img src="previews/aurora.png" width="240" alt="Aurora"></td>
<td>

<strong>31. 极光风</strong> · <em>Aurora</em><br>
<sub>Medium · Dark · 🔥 Trend</sub>

极光风，紫蓝渐变 + 星光点缀，梦幻感、诗意感。

`#0F0C29` `#302B63` `#78C8FF` `#C878FF`

</td>
</tr>
<tr>
<td width="260"><img src="previews/memphis.png" width="240" alt="Memphis"></td>
<td>

<strong>32. 孟菲斯</strong> · <em>Memphis</em><br>
<sub>Advanced · Light · 🔥 Trend</sub>

孟菲斯，鲜艳色块 + 波点/网格图案，玩趣、复古 80s。

`#FFEAA7` `#FF6B6B` `#6C5CE7` `#00CEC9`

</td>
</tr>
<tr>
<td width="260"><img src="previews/pixel.png" width="240" alt="Pixel Art"></td>
<td>

<strong>33. 像素风</strong> · <em>Pixel Art</em><br>
<sub>Medium · Dark</sub>

像素风，8-bit 复古 + 有限调色板，游戏/Nostalgia 产品。

`#1A1C2C` `#E43B44` `#3E8948` `#F0F0DC`

</td>
</tr>
<tr>
<td width="260"><img src="previews/japandi.png" width="240" alt="Japandi"></td>
<td>

<strong>34. 日式北欧</strong> · <em>Japandi</em><br>
<sub>Medium · Light</sub>

日式北欧，米白+木色+黑，禅意与克制的融合。

`#F5F0EB` `#B8A99A` `#3C3A36` `#D4C9BC`

</td>
</tr>
<tr>
<td width="260"><img src="previews/neon.png" width="240" alt="Neon Glow"></td>
<td>

<strong>35. 霓虹灯光</strong> · <em>Neon Glow</em><br>
<sub>Advanced · Dark · 🔥 Trend</sub>

霓虹发光，深底 + 强对比荧光色，夜生活/娱乐类。

`#0A0A0A` `#FF0080` `#00FFFF` `#E0E0E0`

</td>
</tr>
<tr>
<td width="260"><img src="previews/paper.png" width="240" alt="Paper"></td>
<td>

<strong>36. Stationery / 纸质风</strong> · <em>Paper</em><br>
<sub>Easy · Light</sub>

纸质文具风，米黄纸底 + 手写笔迹，温暖手作感。

`#F4EDE4` `#FFFDF7` `#C1A87D` `#4A4035`

</td>
</tr>
<tr>
<td width="260"><img src="previews/hud.png" width="240" alt="Sci-Fi HUD"></td>
<td>

<strong>37. 科幻 HUD</strong> · <em>Sci-Fi HUD</em><br>
<sub>Advanced · Dark</sub>

科幻 HUD，深空底 + 青色数据线条，游戏/军事/太空感。

`#040810` `#00C8FF` `#8CC8D0` `#2A5A65`

</td>
</tr>
<tr>
<td width="260"><img src="previews/pastel.png" width="240" alt="Pastel Soft"></td>
<td>

<strong>38. 柔和粉彩</strong> · <em>Pastel Soft</em><br>
<sub>Easy · Light · 🔥 Trend</sub>

柔和粉彩，淡粉淡蓝，温柔女性向、Gen Z 甜系。

`#FDE2E4` `#E2ECF6` `#FFB5C2` `#9B7ACC`

</td>
</tr>
<tr>
<td width="260"><img src="previews/grunge.png" width="240" alt="Grunge"></td>
<td>

<strong>39. 做旧风</strong> · <em>Grunge</em><br>
<sub>Advanced · Dark</sub>

做旧摇滚，深色纹理 + 撕裂感，音乐/亚文化。

`#1C1A17` `#A83232` `#C4B8A8` `#3A3632`

</td>
</tr>
<tr>
<td width="260"><img src="previews/corp.png" width="240" alt="Corporate"></td>
<td>

<strong>40. 企业蓝</strong> · <em>Corporate</em><br>
<sub>Easy · Light</sub>

企业蓝，标准蓝白 + 清晰层级，B2B/政企类稳妥。

`#F0F4F8` `#2563EB` `#0F172A` `#E2E8F0`

</td>
</tr>
<tr>
<td width="260"><img src="previews/neubr.png" width="240" alt="Neubrutalism"></td>
<td>

<strong>41. 新粗野主义</strong> · <em>Neubrutalism</em><br>
<sub>Easy · Light · 🔥 Trend</sub>

Neo-Brutalism 新粗野，柔色 + 黑边 + 硬阴影，Trending 2024+。

`#F9E4FF` `#FFE566` `#FF90E8` `#000000`

</td>
</tr>
<tr>
<td width="260"><img src="previews/skeu.png" width="240" alt="Skeuomorphism"></td>
<td>

<strong>42. 拟物设计</strong> · <em>Skeuomorphism</em><br>
<sub>Advanced · Light</sub>

拟物设计，真实质感/金属/皮革，怀旧、复古工具感。

`#F2EDE4` `#DDD5C5` `#B07820` `#A09880`

</td>
</tr>
<tr>
<td width="260"><img src="previews/retfut.png" width="240" alt="Retro Futurism"></td>
<td>

<strong>43. 复古未来主义</strong> · <em>Retro Futurism</em><br>
<sub>Medium · Light</sub>

复古未来主义，橘绿米色 + 圆弧几何，70s Space Age。

`#FBF5E6` `#E8743A` `#2A9D8F` `#C66A2E`

</td>
</tr>
<tr>
<td width="260"><img src="previews/bento.png" width="240" alt="Bento Box"></td>
<td>

<strong>44. 便当盒网格</strong> · <em>Bento Box</em><br>
<sub>Easy · Light · 🔥 Trend</sub>

便当盒网格，卡片矩阵布局，Apple 官网同款，最流行 Landing 首选。

`#FFFFFF` `#F2F2F7` `#007AFF` `#1C1C1E`

</td>
</tr>
<tr>
<td width="260"><img src="previews/ainative.png" width="240" alt="AI Native UI"></td>
<td>

<strong>45. AI原生界面</strong> · <em>AI Native UI</em><br>
<sub>Medium · Dark · 🔥 Trend</sub>

AI 原生界面，深色 + 紫色渐变 + 对话流，Copilot 类产品。

`#111111` `#8B5CF6` `#3B82F6` `#A78BFA`

</td>
</tr>
<tr>
<td width="260"><img src="previews/liqglass.png" width="240" alt="Liquid Glass"></td>
<td>

<strong>46. 液态玻璃</strong> · <em>Liquid Glass</em><br>
<sub>Advanced · Light · 🔥 Trend</sub>

液态玻璃 (Apple 2024)，多层玻璃流动、光感通透，全新一代 iOS/macOS 视觉。

`#E8ECF0` `#FFFFFF73` `#648CDC80` `#A064DC80`

</td>
</tr>
<tr>
<td width="260"><img src="previews/spatial.png" width="240" alt="Spatial UI"></td>
<td>

<strong>47. 空间界面</strong> · <em>Spatial UI</em><br>
<sub>Advanced · Light · 🔥 Trend</sub>

空间界面 (Vision Pro)，半透明 + 深度层次，AR/VR 空间感。

`#E4E8EE` `#FFFFFF59` `#508CDC8C` `#8C50DC8C`

</td>
</tr>
<tr>
<td width="260"><img src="previews/hyper3d.png" width="240" alt="3D Hyperrealism"></td>
<td>

<strong>48. 3D超写实</strong> · <em>3D Hyperrealism</em><br>
<sub>Medium · Light · 🔥 Trend</sub>

3D 超写实，真实材质渲染，产品可视化/游戏 UI。

`#FFFFFF` `#6366F1` `#FF6B6B` `#FFE66D`

</td>
</tr>
<tr>
<td width="260"><img src="previews/oled.png" width="240" alt="OLED Dark"></td>
<td>

<strong>49. OLED纯黑</strong> · <em>OLED Dark</em><br>
<sub>Easy · Dark</sub>

OLED 纯黑，绝对黑背景 + 高饱和色，最省电、最沉浸。

`#000000` `#FFFFFF` `#0A84FF` `#1C1C1E`

</td>
</tr>
<tr>
<td width="260"><img src="previews/motionui.png" width="240" alt="Motion Driven"></td>
<td>

<strong>50. 动效驱动</strong> · <em>Motion Driven</em><br>
<sub>Medium · Light · 🔥 Trend</sub>

动效驱动，滚动/hover 动画为主导，Storytelling 型 landing。

`#FFFFFF` `#FF4D4D` `#FF8C00` `#1A1A1A`

</td>
</tr>
<tr>
<td width="260"><img src="previews/kintype.png" width="240" alt="Kinetic Typography"></td>
<td>

<strong>51. 动态字体</strong> · <em>Kinetic Typography</em><br>
<sub>Advanced · Dark</sub>

动态字体，字符本身运动、变形，创意工作室秀肌肉。

`#111111` `#FFFFFF` `#FF3300` `#333333`

</td>
</tr>
<tr>
<td width="260"><img src="previews/parallax.png" width="240" alt="Parallax Storytelling"></td>
<td>

<strong>52. 视差叙事</strong> · <em>Parallax Storytelling</em><br>
<sub>Medium · Light</sub>

视差叙事，多层视差滚动，故事化 landing 首选。

`#F2ECE4` `#C8A87A` `#2A2218` `#8A7A60`

</td>
</tr>
<tr>
<td width="260"><img src="previews/eink.png" width="240" alt="E-Ink Digital"></td>
<td>

<strong>53. 电子墨水</strong> · <em>E-Ink Digital</em><br>
<sub>Easy · Light</sub>

电子墨水，米灰底 + 黑字，Kindle/阅读器/长文体验。

`#F9F6F0` `#1A1814` `#C0B8AC` `#5A5448`

</td>
</tr>
<tr>
<td width="260"><img src="previews/chroma.png" width="240" alt="Chromatic Aberration"></td>
<td>

<strong>54. 色差分离</strong> · <em>Chromatic Aberration</em><br>
<sub>Advanced · Dark</sub>

色差分离，RGB 抖动 + 故障感，音乐/亚文化/实验作品集。

`#0A0A10` `#FF3300` `#00FFFF` `#E0E0E0`

</td>
</tr>
<tr>
<td width="260"><img src="previews/vintage.png" width="240" alt="Vintage Analog"></td>
<td>

<strong>55. 复古胶片</strong> · <em>Vintage Analog</em><br>
<sub>Medium · Light</sub>

复古胶片，暖黄褪色感，摄影/胶片/复刻类。

`#F5E8CC` `#C4A060` `#8B5E3C` `#3A2C18`

</td>
</tr>
<tr>
<td width="260"><img src="previews/dimlayer.png" width="240" alt="Dimensional Layering"></td>
<td>

<strong>56. 维度层叠</strong> · <em>Dimensional Layering</em><br>
<sub>Advanced · Dark</sub>

维度层叠，多层深度 + 高斯模糊，梦境感、诗意 UI。

`#1A1A2E` `#4FC3F7` `#CE93D8` `#E0E4F0`

</td>
</tr>
<tr>
<td width="260"><img src="previews/exmin.png" width="240" alt="Exaggerated Minimalism"></td>
<td>

<strong>57. 夸张极简</strong> · <em>Exaggerated Minimalism</em><br>
<sub>Medium · Light</sub>

夸张极简，超大留白 + 单一元素，设计工作室秀信心。

`#FFFFFF` `#000000` `#F0F0F0` `#CCCCCC`

</td>
</tr>
<tr>
<td width="260"><img src="previews/vibrant.png" width="240" alt="Vibrant Block Based"></td>
<td>

<strong>58. 活力色块</strong> · <em>Vibrant Block Based</em><br>
<sub>Easy · Bold · 🔥 Trend</sub>

活力色块，饱和色 + 硬边分区，运动/娱乐/Gen Z 品牌。

`#FF6B35` `#004E89` `#FCBF49` `#2B2D42`

</td>
</tr>
<tr>
<td width="260"><img src="previews/softui.png" width="240" alt="Soft UI Evolution"></td>
<td>

<strong>59. 柔性UI进化</strong> · <em>Soft UI Evolution</em><br>
<sub>Medium · Light · 🔥 Trend</sub>

柔性 UI 进化，Neomorphism 现代版 + 柔渐变，轻交互产品。

`#E8EDF5` `#D1D9E6` `#F0F4FA` `#7B8794`

</td>
</tr>
<tr>
<td width="260"><img src="previews/genz.png" width="240" alt="Gen Z Chaos Maximalism"></td>
<td>

<strong>60. Z世代混沌</strong> · <em>Gen Z Chaos Maximalism</em><br>
<sub>Advanced · Bold · 🔥 Trend</sub>

Z 世代混沌极繁，撞色 + 手绘 + 混排，反精致美学。

`#FF00FF` `#00FF88` `#FFE600` `#7B61FF`

</td>
</tr>
<tr>
<td width="260"><img src="previews/rawpol.png" width="240" alt="Anti-Polish Raw"></td>
<td>

<strong>61. 反精致美学</strong> · <em>Anti-Polish Raw</em><br>
<sub>Medium · Bold · 🔥 Trend</sub>

反精致原生，粗糙纹理 + 未打磨感，Indie/DIY/独立艺术。

`#F5F0EB` `#2C2C2C` `#E8DDD3` `#8B7355`

</td>
</tr>
<tr>
<td width="260"><img src="previews/tactile.png" width="240" alt="Tactile Digital"></td>
<td>

<strong>62. 触感数字</strong> · <em>Tactile Digital</em><br>
<sub>Medium · Light · 🔥 Trend</sub>

触感数字，皮革/羊毛/纸的数字化质感，温暖工艺品感。

`#F7F3EE` `#D4C5B2` `#8B7355` `#3D3027`

</td>
</tr>
<tr>
<td width="260"><img src="previews/gradmesh.png" width="240" alt="Gradient Mesh"></td>
<td>

<strong>63. 渐变网格</strong> · <em>Gradient Mesh</em><br>
<sub>Medium · Bold · 🔥 Trend</sub>

渐变网格，多点柔和渐变，Stripe 同款，SaaS/AI 通用。

`#667EEA` `#764BA2` `#F093FB` `#4FACFE`

</td>
</tr>
<tr>
<td width="260"><img src="previews/prod3d.png" width="240" alt="3D Product Preview"></td>
<td>

<strong>64. 3D产品展示</strong> · <em>3D Product Preview</em><br>
<sub>Advanced · Bold · 🔥 Trend</sub>

3D 产品展示，深色底 + 3D 渲染物件，硬件/科技产品官网。

`#0A0A0A` `#1A1A2E` `#E0E0E0` `#00D4FF`

</td>
</tr>
<tr>
<td width="260"><img src="previews/cursor.png" width="240" alt="Interactive Cursor"></td>
<td>

<strong>65. 交互光标</strong> · <em>Interactive Cursor</em><br>
<sub>Advanced · Bold · 🔥 Trend</sub>

交互光标，自定义光标 + hover 特效，Interactive Storytelling。

`#1A1A1A` `#FFFFFF` `#FF4444` `#FFD700`

</td>
</tr>
<tr>
<td width="260"><img src="previews/microix.png" width="240" alt="Micro Interactions"></td>
<td>

<strong>66. 微交互</strong> · <em>Micro Interactions</em><br>
<sub>Medium · Light · 🔥 Trend</sub>

微交互，细节动效 + 精致 hover 反馈，Craft-driven 产品。

`#FAFBFC` `#24292E` `#0366D6` `#28A745`

</td>
</tr>
<tr>
<td width="260"><img src="previews/zeroint.png" width="240" alt="Zero Interface"></td>
<td>

<strong>67. 零界面</strong> · <em>Zero Interface</em><br>
<sub>Advanced · Light · 🔥 Trend</sub>

零界面，看不见的 UI，语音/AI 优先，未来主义极简。

`#FFFFFF` `#111111` `#F5F5F5` `#999999`

</td>
</tr>
</table>

每个风格条目在 [`styles-reference.md`](./styles-reference.md) 里都包含：完整调色板（7+ token 带角色）、可复制的 CSS snippet、3 种 prompt 模板（Basic / Advanced / Keywords）、Do's & Don'ts、DNA 分数、3 个相关风格。

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
