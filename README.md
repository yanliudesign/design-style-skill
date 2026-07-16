# design-style

A Claude Code / Copilot **skill** that recommends and applies design styles from a curated library of 67 visual aesthetics — from Brutalism to Glassmorphism, Cyberpunk to Japandi.

**Live reference:** https://design-lab-yanliu.vercel.app/

## What it does

- Recommends 3 design styles for your project (opinionated, context-aware)
- Outputs ready-to-paste CSS variables, colors, fonts, and prompt templates
- Looks up any of the 67 styles by name
- Applies a chosen style to your existing code

## Files

- [`SKILL.md`](./SKILL.md) — Skill definition (frontmatter + instructions).
- [`styles-reference.md`](./styles-reference.md) — The 67-style reference, auto-generated from [`design-style-lab.html`](https://design-lab-yanliu.vercel.app/).

## Install (Claude Code / Anthropic skills)

Drop this folder into `~/.claude/skills/design-style/`. Claude will pick it up automatically the next time it activates.

## Trigger phrases

- "recommend a design style"
- "帮我选设计风格" / "推荐设计风格"
- "use glassmorphism" / "apply brutalist style"
- "what style should I use for my project?"
