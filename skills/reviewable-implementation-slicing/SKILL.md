---
name: reviewable-implementation-slicing
description: >-
  Split an implementation into reviewable slices with a plan. Use this skill when the author asks to prepare for reviews.
---

# Reviewable Implementation Slicing

The goal is simple: to maximize reviewer happiness and minimize reviewer effort.

## Workflow

1. Create a new plan using [references/plan-template.md](references/plan-template.md)
2. Slice by one coherent theme per slice with a limit of 25 files.
3. Ask the author for a binary reaction: **lgtm** or **rework because [insert reason]**
4. Commit with message being the combination of implementation type, feature name, slice number, and slice description e.g. `feat/chat:1 - create message model`
5. Upon receiving a review
    - Approved -> Update the plan and go back to step 2 until there's nothing else to review
    - Rejected -> Choose the reset by what failed:
        - **Soft reset** — The feedback targets this slice’s implementation details (bugs, style, API shape within the agreed design). Rework stays inside the same slice and commit scope; architecture and the plan stay as-is.
        - **Hard reset** — The feedback challenges an architecture decision (boundaries, persistence model, major abstraction). Revisit the plan and slices from the top; local fixes at the commit are not enough.

## Rules

- DO NOT mix unrelated files into one slice.
- DO NOT use slices to skip tests or security.

## Out of Scope 

- PR branching: because all codes will be commited locally
- Feature Design
