<div align="center">

[中文](./README.zh.md) · **English**

# 🎨 Design Style Skill

---

**Pick and apply a design style from 67 curated aesthetics — in 3 steps.**

[![License](https://img.shields.io/badge/LICENSE-MIT-4c8bf5?style=flat-square&labelColor=333)](./LICENSE)
[![Version](https://img.shields.io/badge/VERSION-1.0.0-2ea44f?style=flat-square&labelColor=333)]()
[![Stars](https://img.shields.io/github/stars/yanliudesign/design-style-skill?style=flat-square&label=STARS&color=e37f2c&labelColor=333)](https://github.com/yanliudesign/design-style-skill/stargazers)

[![Claude Code](https://img.shields.io/badge/Claude_Code-Skill-d97757?style=flat-square&labelColor=1a1a1a&logo=anthropic&logoColor=white)](https://claude.ai/code)
[![Codex](https://img.shields.io/badge/Codex-Skill-2ea44f?style=flat-square&labelColor=1a1a1a)]()
[![OpenCode](https://img.shields.io/badge/OpenCode-Skill-4c8bf5?style=flat-square&labelColor=1a1a1a)]()
[![OpenClaw](https://img.shields.io/badge/OpenClaw-Skill-8b5cf6?style=flat-square&labelColor=1a1a1a)]()
[![Hermes](https://img.shields.io/badge/Hermes-Skill-e879a8?style=flat-square&labelColor=1a1a1a)]()

</div>

> 🧪 Interactive lab: browse all **67 styles** — colors, CSS, prompt templates — at **[design-lab-yanliu.vercel.app](https://design-lab-yanliu.vercel.app/)**.

An agent skill for picking a design style. Tell it what you're building and the feeling you want, and it hands back **3 opinionated recommendations** — each with a real color palette, ready-to-paste CSS variables, font suggestions, and a prompt template. Pick one, and it integrates the style into your existing code (Tailwind, vanilla CSS, styled-components, plain HTML). Not a moodboard, not 15 vague options — 3 concrete choices you can ship today.

---

## How it works — just 3 steps

Invoke the skill with anything like *"help me pick a design style"* / *"apply glassmorphism to my landing page"* / *"帮我选设计风格"* and you go through exactly:

1. **Tell me the project + vibe** — one question about what you're building (SaaS / portfolio / e-commerce / blog / landing), one about the feeling (professional / bold / warm / minimal). If your first message already covers both, this step is skipped.
2. **Get 3 style recommendations** — each with a one-line reason it fits, a 4-color palette, DNA scores (Roundness / Contrast / Warmth), and a 2-sentence "why this over the others."
3. **Apply it to your code** — pick one, and the skill scans your existing project (Tailwind config? CSS variables? styled-components?) and injects the palette / fonts / radii / shadows *in your project's own idiom*, plus a Google Fonts / Fontshare `<link>` and a sample styled component (card / button / nav) to sanity-check.

Three side entrances exist:

- **Lookup mode** — *"tell me about glassmorphism"* skips straight to Phase 3 and shows the full style card.
- **Apply-only mode** — *"apply cyberpunk to this file"* skips recommendation and jumps to Phase 4.
- **Direct name mode** — mention a style name in any query and it's treated as the chosen style.

---

## The 67 styles at a glance

Grouped by innovation level, matched to project type. Below is a sampler — the full library lives in [`styles-reference.md`](./styles-reference.md) and interactively at **[design-lab-yanliu.vercel.app](https://design-lab-yanliu.vercel.app/)**.

| Level | Vibe | Example styles |
|-------|------|----------------|
| **1 · Conservative** | Professional, trustworthy, corporate-safe | Corporate Clean · Japandi · Minimalist · Editorial Serif · Swiss Grid |
| **2 · Modern** | Clean, contemporary, most SaaS defaults | Glassmorphism · Neumorphism · Nordic · Material 3 · Soft UI |
| **3 · Distinctive** | Opinionated, memorable, signature-worthy | Brutalism · Bento Grid · Terminal · Y2K Aero · Editorial Magazine |
| **4 · Experimental** | Bold, risk-taking, portfolio-grade | Cyberpunk · Vaporwave · Memphis · Anti-Design · Glitchcore |

Each style entry includes: full color palette (7+ tokens with roles), a copy-paste CSS snippet, 3 prompt templates (Basic / Advanced / Keywords), Do's and Don'ts, DNA scores, and 3 related styles.

---

## Four principles

1. **Show, don't lecture** — Lead with concrete CSS, colors, and prompt templates. Not theory, not history lessons, not "what is design."
2. **Context-aware** — A fintech dashboard needs different styles than an indie game landing page. Recommendations are always grounded in *your* project.
3. **Opinionated** — Always 3, never 15. Explain *why* each fits your specific case, not "here are some options."
4. **Immediately actionable** — Every output is CSS variables, prompt strings, and code you can paste right now. No "explore further" homework.

---

## File structure

```
design-style-skill/
├── SKILL.md                # Entry · 4 phases (Detect / Understand / Show / Apply)
├── styles-reference.md     # The 67-style library — colors, CSS, prompts, DNA scores
└── README.md               # This file
```

The interactive companion (the visual lab you actually click through) lives at **[design-lab-yanliu.vercel.app](https://design-lab-yanliu.vercel.app/)** — that's the source of truth for the style library.

---

## How it thinks

- **Style is a shortcut for intent.** Picking "Glassmorphism" vs "Brutalism" isn't cosmetic — it declares who you are, what you value, and who you're excluding. The skill treats style choice as a positioning decision, not a decoration one.
- **3 is the right number.** One is dictatorial; 15 is decision paralysis. Three lets a user compare while still being *forced* to argue for a preference.
- **DNA scores beat category labels.** "Glassmorphism" is a label; *Roundness 3 / Contrast 2 / Warmth 2* is a coordinate. Coordinates let you swap between styles that share DNA even if the label sounds different.
- **Apply > describe.** A style is only useful when it's in the codebase. The skill's real deliverable is the moment your project starts *looking* like the style, not a paragraph about the style.

---

## Related links

- 🧪 **[design-lab-yanliu.vercel.app](https://design-lab-yanliu.vercel.app/)** — interactive 67-style lab (colors, prompts, one-click copy)
- 📚 [`styles-reference.md`](./styles-reference.md) — full library as a single Markdown reference
- 🧠 [`SKILL.md`](./SKILL.md) — the skill's routing, phases, and guardrails

---

## License

MIT — fork it, remix it, ship your own version.

Created by [Dreameryanyan](https://www.linkedin.com/in/yanliudesign/) · [LinkedIn](https://www.linkedin.com/in/yanliudesign/) · [X](https://x.com/yanliudreamer) · [Xiaohongshu](https://www.xiaohongshu.com/notification)
