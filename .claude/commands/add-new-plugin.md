---
name: add-new-plugin
description: Workflow command scaffold for add-new-plugin in Vencord.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-new-plugin

Use this workflow when working on **add-new-plugin** in `Vencord`.

## Goal

Adding a new plugin, typically by creating a new folder and main file, and updating constants.

## Common Files

- `src/plugins/*/index.tsx`
- `src/plugins/*/index.ts`
- `src/utils/constants.ts`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Create new plugin folder under src/plugins
- Add main plugin file (index.ts or index.tsx)
- Update src/utils/constants.ts to register the plugin
- Commit with a message referencing the new plugin

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.