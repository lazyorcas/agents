---
name: brand-design
description: Facilitates discovery of brand decisions and drafts or updates BRANDING.md at the repository root. Use when the author wants to create, revise, or expand a branding document, define emotions, vibes, colors, typography, composition, dark mode, or inspiration references for a product.
---

# Brand Designer

> [!IMPORTANT]
> TODO:
> - Add a "Security & Privacy" section.

Help the author produce a **single source of truth** for branding: typically `BRANDING.md` in the project root. The file should be concise and straightforward for engineers to work with.

## Workflow

1. **Scoping**: New `BRANDING.md` or replace/merge sections in the existing file?
2. **Discovery**: Run through [Discovery Questions](#discovery-questions). If the author already answered some, skip those.
4. **Iterate**: If the repo already has `BRANDING.md`, preserve sections the author did not ask to change; merge new answers into the right sections.

## Discovery Questions

Ask only what is still unknown. Group them mentally as: brand personality → visual system → layout rules → constraints.

**Product & Audience**

- What is the product (one sentence)? Who is it for?
- What should users *feel* when using it (emotions)?
- How should it be *perceived* (adjectives / vibes: bold, calm, premium, etc.)?

**Color**

- What is the color palette?
    - Start with [a Tailwind color](https://tailwindcss.com/docs/colors)
    - Use [shadcn theme tokens](https://ui.shadcn.com/docs/theming)

**Typography**

- What are the font names for:
  - Display / headings?
  - Body / UI?

Rules:
- Limit to max. 2 font families.
- Use [Fontshare](https://www.fontshare.com/) and [Google Fonts](https://fonts.google.com/).

**Inspiration & boundaries**

- Ask for inspirations from other products (links). 
    - Be helpful and give suggestions if nothing comes in mind for the author.

## Output template

When writing or rewriting `BRANDING.md`, start from this shape. Replace placeholders with project-specific content; omit sections the author explicitly does not want.

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

## Out of scope

The following topics are out of scope unless explicitly requested.

- Implementing components, CSS, or Storybook stories.
- Logo design, trademark, or legal review of third-party assets.
