---
name: brand-design
description: Produce branding guidelines with a verbal description and a visual implementation of the brand. Use this skill when the author wants to create, revise, or expand the branding.
---

# Brand Designer

Help the author produce a **single source of truth** for branding: 
- `BRANDING.md`: verbal description of the brand
- `BRANDING.html`: visual implementation of the brand

Both files should be placed in the project root.

## Workflow

1. **Scoping**: New `BRANDING.md` or replace/merge sections in the existing file?
2. **Discovery**: Run through [Discovery Questions](#discovery-questions). If the author already answered some, skip those.
3. **Write**: Create/update the `BRANDING.md`.
4. **Show**: Generate and replace the `BRANDING.html` file.

## Discovery Questions

Ask only what is still unknown. Group them mentally as: brand personality, visual system.

### Product & Audience

- What is the product (one sentence)? Who is it for?
- What should users *feel* when using it (emotions)?
- How should it be *perceived* (adjectives / vibes: bold, calm, premium, etc.)?

### Color Theme

- What is the color palette?
    - Ask the author to start with [a Tailwind color](https://tailwindcss.com/docs/colors)
    - Use [shadcn theme tokens](https://ui.shadcn.com/docs/theming)

### Typography

- What are the font names for:
  - Display / headings?
  - Body / UI?

Rules:
- Limit to max. 2 font families.
- Use [Fontshare](https://www.fontshare.com/) and [Google Fonts](https://fonts.google.com/).

### Inspirations

- Ask for inspirations from other products (links). 
    - Be helpful by giving suggestions if nothing comes in mind for the author.

## `BRANDING.md` template

```md
# BRANDING.md

This file provides an overview of the branding of the project.

## Branding

### Emotions

[Product name] should provoke the following feelings and emotions:
- …

### Vibes

[Product name] should be perceived as:
- …

### Color

[Palette reference or link]

Tokens:
- `primary`: …
- `secondary`: …
- …

### Typography

- Headings & Display: …
- Body & Paragraph: …

## Inspirations

- [Name](https://…)

Do not copy the inspirations directly. Adapt the patterns to [product]’s brand voice.
```

## Generating `BRANDING.html`

1. Follow the instructions in [Tailwindcss's Play CDN setup](https://tailwindcss.com/docs/installation/play-cdn) to initialize `BRANDING.html`
2. Add (inline) the theme
3. Add (inline) a marketing page with hero and feature sections.

## Out of scope

The following topics are out of scope unless explicitly requested.

- Logo design, trademark, or legal review of third-party assets.
