---
name: design-style
description: Recommend and apply design styles from a curated library of 67 visual aesthetics. Use when the user wants to choose a design style for their project, get style recommendations, or apply a style's CSS/colors/fonts to their code.
---

# Design Style

Recommend and apply design styles from a curated library of 67 visual aesthetics — from Brutalism to Glassmorphism, Cyberpunk to Japandi.

## When This Skill Activates

- User asks "what style should I use for my project?"
- User says "recommend a design style"
- User mentions a specific style name ("use glassmorphism", "apply brutalist style")
- User wants to apply colors, fonts, or CSS from a design aesthetic
- User asks "帮我选设计风格" / "推荐设计风格" / "选个设计风格"

## Core Principles

1. **Show, don't lecture** — Lead with concrete CSS, colors, and prompt templates. Not theory.
2. **Context-aware** — A fintech dashboard needs different styles than an indie game landing page.
3. **Opinionated** — Recommend 3 styles, not 15. Explain *why* each fits.
4. **Immediately actionable** — Every run ends with a browsable comparison HTML the user can pick from, plus paste-ready CSS variables.
5. **No middle stops** — After the user provides purpose + basic info, run straight through to a generated preview. Don't stop to ask "which one do you prefer?" — let the visual do the choosing.

---

## Phase 0: Detect Mode

- **Mode A: Recommend** (default) — User wants styles picked for their project. Go to Phase 1.
- **Mode B: Lookup** — User names a specific style (*"tell me about glassmorphism"*). Skip Phase 1/2, go straight to Phase 3 for that style.
- **Mode C: Apply** — User picks a style and wants it applied to existing code (*"apply cyberpunk to this file"*). Skip Phase 1/2/3, go straight to Phase 4.

---

## Phase 1: Two Questions — Purpose + Basic Info

**Combine both into a single `AskUserQuestion` call.** Do NOT ask them one at a time.

### Question 1 — Purpose (目的)

**Header:** `Purpose`
**Question:** "What are you building, and what's the goal? / 你在做什么？想达成什么目的？"
**Options** (with freeform allowed):
- SaaS / 工具产品
- 作品集 / 个人站
- 电商 / 品牌店
- 博客 / 内容站
- Landing Page / 营销落地页
- App / 移动端
- 演示 / Slides / 演讲
- 其他 (freeform)

### Question 2 — Basic Info (基本信息)

**Header:** `Basics`
**Question:** "Tell me a bit more — brand vibe, audience, must-have/avoid colors, any constraints. / 说几句项目基本信息：品牌调性、目标用户、必须保留或规避的颜色、任何限制。"
**No fixed options — freeform text answer.**

Example acceptable answers:
- *"AI dev tool, targeting engineers, must feel technical, no baby pastels"*
- *"独立摄影师作品集，想要暗色高级感，偏冷色调"*
- *"儿童教育 App，家长掏钱，得让家长放心又让孩子觉得有趣"*

**Skip Phase 1 entirely** if the user's initial message already covers both (e.g., *"帮我给我的 AI dev SaaS 找 3 个大胆但可信的风格"* — that answers Purpose + Basics inline).

---

## Phase 2: Pick 3 Styles + Auto-Generate Preview

**No middle stop.** After Phase 1, immediately do all of the following in one turn:

### Step 2.1 — Read the reference

Read [styles-reference.md](styles-reference.md) — the "Use Case Recommendations" section for the user's Purpose category, and the full detail blocks (`### N. id — Name / 中文名`) for candidate styles.

### Step 2.2 — Infer innovation level from Basic Info

Parse the free-text answer for signals:

| Signal words in Basics | Innovation level |
|---|---|
| trustworthy, professional, safe, financial, enterprise, 稳重, 可信, 专业 | **Level 1** |
| clean, modern, standard SaaS, 现代, 干净 | **Level 2** |
| bold, distinctive, signature, memorable, 大胆, 有辨识度, 有记忆点 | **Level 3** |
| experimental, rule-breaking, avant-garde, portfolio-grade, 先锋, 实验, 冒险, 作品集级 | **Level 4** |

If ambiguous, default to **Level 2–3** (the sweet spot for most projects).

### Step 2.3 — Choose 3 styles with real spread

Pick 3 styles that **span the axis** — not 3 flavors of the same thing. Rules of thumb:

- One "safest" pick that clearly matches the level.
- One "signature" pick that leans one level bolder.
- One "wildcard" from an adjacent Purpose category that could reframe the project (e.g., for a SaaS pick, throw in an Editorial or Kinetic option).

Avoid recommending 3 styles that share the same DNA quadrant (e.g., three dark-neon styles). The 3 should feel visually **distinct**.

### Step 2.4 — Print the recommendation card (3 blocks)

```
## Style Recommendations

### 1. [Name] · [中文名] — [one-line reason it fits this project]
Colors: ■ #hex ■ #hex ■ #hex ■ #hex
DNA: Roundness X | Contrast X | Warmth X
Why: [2 sentences tied to the user's Purpose + Basics — not generic style copy]

### 2. [Name] · [中文名] — [one-line reason]
...

### 3. [Name] · [中文名] — [one-line reason]
...
```

### Step 2.5 — Generate a side-by-side comparison HTML

**Immediately** (in the same turn — do NOT ask the user "which one do you prefer?"), create a single-file HTML that renders the **same sample content** in all 3 chosen styles side-by-side:

- **Save path:** `~/Desktop/Claude skills/design-style-preview-<project-slug>.html`
- **Sample content:** a hero card the user can imagine as their landing page — brand name (from Basics if given, else "Your Project"), a tagline, a primary CTA button, 3 feature chips. Same content in each of the 3 style renders.
- **Layout:** 3 columns on desktop (`grid-template-columns: repeat(3, 1fr)`), stacked on mobile.
- **Each column** displays: style number & name at top, then the rendered card using that style's CSS from styles-reference.md.
- **Include** a "Pick this one" button under each render that copies the style ID to clipboard.
- **Open the file** with `open <path>` at the end of the turn.

### Step 2.6 — Print the follow-up prompt

End the turn with:

> *"Preview opened. Tell me which one clicks — or say 'wildcard 3 more' and I'll pull a different trio."*

---

## Phase 3: Show Style Details (Lookup Mode)

Only used when the user names a specific style directly (Mode B) or after they pick one from the Phase 2 preview.

Read the style's full entry in [styles-reference.md](styles-reference.md) and present:

1. **Overview** — Name, difficulty, DNA scores
2. **Color Palette** — All colors with their roles, as a visual table
3. **CSS Snippet** — The core CSS that defines this style
4. **Font Recommendations** — Extract from the CSS/prompts what fonts work best
5. **Prompt Templates** — All 3 prompt templates (Basic, Advanced, Keywords)
6. **Do's and Don'ts** — Quick reference for staying on-style
7. **Related Styles** — 3 similar styles for exploration

Then offer: *"Want me to apply this to your project? (Phase 4)"*

---

## Phase 4: Apply to Project

Triggered when the user picks a favorite from the Phase 2 preview OR explicitly asks to apply a style.

### 4.1 Generate CSS Variables

```css
:root {
  /* [Style Name] Theme */
  --color-primary: #...;
  --color-secondary: #...;
  --color-accent: #...;
  --color-background: #...;
  --color-surface: #...;
  --color-text: #...;
  --color-text-secondary: #...;

  --font-heading: '...', ...;
  --font-body: '...', ...;

  --radius-sm: ...;
  --radius-md: ...;
  --radius-lg: ...;

  --shadow: ...;
}
```

### 4.2 Scan the user's project

Read existing CSS/HTML/framework files to detect: Tailwind, vanilla CSS variables, CSS Modules, styled-components, and any existing theme tokens.

### 4.3 Apply *in the project's own idiom*

- **Tailwind** → `theme.extend` config with the palette, fonts, shadows.
- **CSS Variables** → a `:root` block (or update existing tokens).
- **Styled-components / CSS Modules** → a theme object.
- **Raw HTML** → inject a `<style>` block or inline styles.

Also provide:
- Google Fonts / Fontshare `<link>` for recommended fonts
- A sample component (card, button, nav) styled in the chosen aesthetic
- The 3 prompt templates for generating more UI with AI tools

### 4.4 Verify

- WCAG AA contrast on primary/text combos
- Font links properly included
- No overrides that break existing components

---

## Data Source

All style data comes from [styles-reference.md](styles-reference.md):
- Quick index of all 67 styles with colors, difficulty, and tags
- Use case recommendations by project type and innovation level
- Full details per style: colors, CSS, prompts, do's/don'ts, DNA scores

The authoritative interactive reference: https://design-lab-yanliu.vercel.app/

---

## Guardrails

- **Never** recommend more than 3 styles at once — too many options paralyze.
- **Never** stop between Phase 1 and Phase 2's HTML output — the point of this skill is to *let the user see the preview before they decide*, not to interview them further.
- **Always** ground recommendations in the user's Purpose + Basics — no generic "these are popular styles."
- When applying styles, preserve existing code structure — don't rewrite files.
- If the user's project has an established design system, integrate with it rather than override.
- Font recommendations must use Google Fonts or Fontshare (free, no licensing issues).
- Check color contrast when applying dark or low-contrast styles.
