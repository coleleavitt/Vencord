---
name: plugin-bugfix-update
description: Workflow command scaffold for plugin-bugfix-update in Vencord.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /plugin-bugfix-update

Use this workflow when working on **plugin-bugfix-update** in `Vencord`.

## Goal

Fixing bugs or updating existing plugins, often touching one or more plugin index/component files.

## Common Files

- `src/plugins/*/index.tsx`
- `src/plugins/*/index.ts`
- `src/plugins/*/components/*.tsx`
- `src/plugins/*/utils.ts`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Identify plugin(s) with bug or needed update
- Edit the plugin's main file (e.g., index.tsx or index.ts)
- Optionally update related component or utility files within the plugin folder
- Commit with a message referencing the plugin(s) and the fix

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.