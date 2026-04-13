# AGENTS.md

> [!NOTE]
> Copy and paste this file to your project.

This file provides guidance to AI coding agents working with this repository.

## Reading Requirements

- Read [README.md](README.md) for an overview of the project.

## Core Principles

1. **Maximize developer happiness**: Maximize for reviewability and maintainability of human developers.
2. **Take the shortest route**: Minimize customization. Always attempt with existing code, popular libraries, or popular patterns.
3. **Ask until fully clear**: Ask as many questions as you need to understand the context, scope, and requirements.
4. **Be pragmatic**: Justify technical decisions with reasons aligned with the scope and size of the project.
5. **Contradiction is okay once**: My instructions might contradict with what you are told from time to time. Suggest changes to this file and other skills when that happens.

## Core Workflows

### Implementing a new feature

1. Write a high-level feature design in `docs/features/<feature-slug>/DESIGN.md`
2. **Prototype**: Make the feature work
    - Maximize delivery speed
    - Skip most rules, except security & privacy
3. Ask the developer to test the feature
4. **Finalize**: Make the code easy to review and maintain

## Developer Happiness

Other skills might also include a section dedicated to maximizing developer happiness.

Here are some base rules:
- **Separation of Concerns**: Each code unit should be concerned with one and only-one thing. To test this: ask yourself if you can describe this with a one-sentence purpose statement.
- **Prefer Short Functions**: Minimize LoCs to a soft limit of 20 lines per function. Otherwise, move some logic into smaller single-responsibility functions.
- **Prefer Small Files**: Minimize LoCs to a soft limit of 200 lines per file. Otherwise, split the big file into smaller files.
- **Avoid Inline Comments**: The code should explain itself.

## Terminology

- Author: the person who provides you with a task or set of instructions to perform
- Developer: same as an Author

## Keep in mind

- If/When a code snippet is provided, it is simplified for getting the point across faster by skipping the obvious e.g. syntax.
