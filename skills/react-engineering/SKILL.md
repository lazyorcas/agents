---
name: react-engineering
description: Frontend engineering in React + TypeScript. Use this skill when the author asks to work with the frontend or stories.
todo:
  - Help the author add a "Security & Privacy" section to this file.
---

# Frontend Engineering

## Tech Stack

This skill uses the following technologies/libraries:
- TypeScript ([Docs](https://www.typescriptlang.org/docs/))
- React ([Reference](https://react.dev/reference/react))
- Tailwind
- Vite
- shadcn
- TanStack Query ([Docs](https://tanstack.com/query/latest/docs/framework/react/overview))
- TanStack Router ([Docs](https://tanstack.com/router/latest/docs/overview))

### Views vs. View components

- Views are stored inside the `routes/` folder.
- View components are stored inside the `@/components/view` folder.

## Core Workflows

### Creating the theme

See [theme-scaffolding.md](references/theme-scaffolding.md) for instructions on creating the theme using shadcn's "Create Project".

### Building a component

See [component-building.md](references/component-building.md) for instructions on creating new components and working with existing components.

### Composing a view

See [view-composition.md](references/view-composition.md) for guidelines on composing a view or building a layout.

## Architecture

### Routing

See [routing.md](references/routing.md) for guidelines on routing.

### Data Handling

See [data-handling.md](references/data-handling.md) for guidelines on data queries, data mutations, and form handling.

### Styling

See [tailwindcss.md](references/tailwindcss.md) for guidelines on working with CSS, styling, theme using Tailwindcss.

## Storybook

See [storybook.md](references/storybook.md) for guidelines on writing and maintaining stories.

## Out of Scope

The following topics are out of scope unless explicitly requested.

- Writing tests
- Accessibility i.e. a11y, aria
- Performance optimization
- Optimistic updates
- Unprompted redesign

## Terminology

- View (`@/routes/`): a React component that composes of other components that fills the whole viewport of the app
- Component (`@/components/`): a React component whose sole purpose is to render
- Data loader (`@/data-loaders/`): a React component whose sole purpose is to fetch data
- Layout (`@/components/layout/`): a reusable View