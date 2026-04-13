---
name: reviewable-implementation-slicing
description: >-
  Package a finalized local implementation into ordered self-review slices on this machine. You plan and run git while the author reviews each slice; you may need to rework. Use when the author asks to prepare for reviews.
---

# Reviewable Implementation Slicing

The goal is simple: turn a finished implementation into slices the author can **review locally**, one at a time, without losing what comes later.

## Responsibilities

- The author only reviews: read the slice, run checks if they want, then tell you "lgtm" or "rework" (with a reason on rework).
- You do everything else: organize the plan, run `git`, commit, stash and unstash, update the plan, and carry out rework.

## Workflow

1. Create a new plan from [references/plan-template.md](references/plan-template.md) and organize the implementation into ordered slices.

2. Group into one coherent theme per slice with a limit of ~25 files. Only slice *k* is on the review surface; stash everything for later slices (after slice *k*). Pick one git pattern for the whole run and stick to it:
   - Commit-then-stash: `git add` only slice *k*, commit (message = implementation type + feature name + slice number + slice description, e.g. `feat/chat:1 - create message model`), then `git stash push` the still-uncommitted rest.
   - Stash-then-commit: `git stash push` paths for slice *k*+1 onward so the tree is only slice *k*; after "lgtm" in step 3, you commit slice *k* with that same message shape, then unstash for the next cycle.

   You name stashes so the remainder is obvious, keep one ordered remainder, and add a one-liner in the plan if the unstashed blob is awkward to split on the next pass.

3. The author self-reviews on this machine and tells you: "lgtm" or "rework" (with a reason on rework). Then you act on what they said:
   - "lgtm" — If you are on stash-then-commit and slice *k* is not committed yet, commit it now (same message shape as in the commit-then-stash bullet in step 2). You update the plan. If anything was stashed for later: unstash, go back to step 2 for the next slice (re-stash what is still after that). Repeat until there is nothing left to review.
   - "rework" — You choose the reset by what failed, based on the reason the author gave:
     - **Soft reset** — The feedback targets this slice’s details (bugs, style, API shape within the agreed design). You rework inside the same slice and stash boundary; architecture and the plan stay as-is.
     - **Hard reset** — The feedback challenges architecture (boundaries, persistence model, major abstraction). You revisit the plan and slices from the top; local fixes on this slice alone are not enough.

## Rules

- **DO NOT** mix unrelated files into one slice.
- **DO NOT** use slices to skip tests or security.
- **DO NOT** stash in a way that scrambles order—later slices must still come out of stash in a sensible sequence.

## Out of Scope

- PR branching: all of this is local commits/stashes on this machine.
- Feature design: the implementation is already finalized; this skill only packages it for review.
