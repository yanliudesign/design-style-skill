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
- User asks "帮我选设计风格" or "推荐设计风格"

## Core Principles

1. **Show, don't lecture** — Lead with concrete CSS, colors, and prompt templates. Not theory.
2. **Context-aware** — A fintech dashboard needs different styles than an indie game landing page.
3. **Opinionated** — Recommend 3 styles, not 15. Explain *why* each fits.
4. **Immediately actionable** — Output CSS variables and code the user can paste right now.

---

## Phase 0: Detect Mode

Determine what the user wants:

- **Mode A: Recommend** — User describes a project/vibe, wants style recommendations. Go to Phase 1.
- **Mode B: Lookup** — User names a specific style (e.g., "tell me about glassmorphism"). Go to Phase 3 directly for that style.
- **Mode C: Apply** — User wants to apply a style to existing code. Go to Phase 1 if no style chosen yet, or Phase 4 if style is specified.

---

## Phase 1: Understand the Project

Ask up to 2 questions (combine into one AskUserQuestion call):

**Question 1 — Project Type** (header: "Project"):
What are you building?
Options:
- SaaS / Tool
- Portfolio / Personal site
- E-commerce
- Blog / Content
- Landing page / Marketing

**Question 2 — Vibe** (header: "Vibe"):
What feeling should it evoke?
Options:
- Professional & trustworthy
- Bold & cutting-edge
- Warm & approachable
- Minimal & refined

If the user already described both project type and vibe in their initial message, skip the questions entirely and proceed to Phase 2.

---

## Phase 2: Recommend 3 Styles

**Read [styles-reference.md](styles-reference.md)** — specifically the "Use Case Recommendations" section to find styles that match the user's project type and desired innovation level.

Map user vibe to innovation level:
- Professional & trustworthy → Level 1-2
- Bold & cutting-edge → Level 3-4
- Warm & approachable → Level 1-2
- Minimal & refined → Level 2-3

Present exactly **3 style recommendations** in this format:

```
## Style Recommendations

### 1. [Style Name] — [one-line reason why it fits]
Colors: ■ #hex ■ #hex ■ #hex ■ #hex
DNA: Roundness X | Contrast X | Warmth X
Why: [2 sentences explaining the match to their project]

### 2. [Style Name] — ...
...

### 3. [Style Name] — ...
...
```

Then ask which one they prefer (or if they want to explore a different direction).

---

## Phase 3: Show Style Details

Once a style is chosen (or user asked about a specific style), read the style's full entry in [styles-reference.md](styles-reference.md) and present:

1. **Overview** — Name, description, difficulty, DNA scores
2. **Color Palette** — All colors with their roles, displayed as a visual table
3. **CSS Snippet** — The core CSS that defines this style
4. **Font Recommendations** — Extract from the CSS/prompts what fonts work best
5. **Prompt Templates** — All 3 prompt templates (Basic, Advanced, Keywords)
6. **Do's and Don'ts** — Quick reference for staying on-style
7. **Related Styles** — 3 similar styles for exploration

Format the output cleanly. This is the user's style reference card.

---

## Phase 4: Apply to Project

When the user wants to apply a style to their code:

### Step 4.1 — Generate CSS Variables

Create a `:root` CSS variable block from the chosen style:

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

### Step 4.2 — Scan Current Project

Read the user's existing CSS/HTML/framework files to understand:
- What CSS framework (Tailwind, vanilla, CSS modules, styled-components)?
- What existing color variables or theme system exists?
- What font loading strategy is in place?

### Step 4.3 — Apply

Based on the scan:
- **Tailwind**: Generate a `theme.extend` config with the style's colors, fonts, and shadows
- **CSS Variables**: Create or update a `:root` block with the style's tokens
- **Styled Components / CSS Modules**: Generate a theme object
- **Raw HTML**: Inject inline styles or a `<style>` block

Also provide:
- Google Fonts / Fontshare `<link>` tag for recommended fonts
- A sample component styled in the chosen aesthetic (card, button, nav)
- The style's prompt templates for generating more UI with AI tools

### Step 4.4 — Verify

After applying, check that:
- Colors have sufficient contrast (WCAG AA)
- Font links are properly included
- The style is consistent across the applied components

---

## Data Source

All style data comes from [styles-reference.md](styles-reference.md), which contains:
- Quick index of all 67 styles with colors, difficulty, and tags
- Use case recommendations by project type and innovation level
- Full details for each style: colors, CSS, prompts, do's/don'ts, DNA scores

The authoritative interactive reference is: https://design-lab-yanliu.vercel.app/

---

## Guardrails

- Never recommend more than 3 styles at once — too many options paralyze
- Always ground recommendations in the user's project context
- When applying styles, preserve existing code structure — don't rewrite files
- If the user's project has an established design system, integrate with it rather than override
- Font recommendations should use Google Fonts or Fontshare (free, no licensing issues)
- Check color contrast when applying dark or low-contrast styles
