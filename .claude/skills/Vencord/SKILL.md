```markdown
# Vencord Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns, coding conventions, and common workflows for contributing to the Vencord project—a TypeScript-based codebase for plugin-driven Discord enhancements. You will learn how to add and update plugins, enhance the settings UI, refactor modal components, and follow the project's established code style.

## Coding Conventions

- **File Naming:**  
  Use `camelCase` for files and folders.  
  _Example:_  
  ```
  src/plugins/myPlugin/index.tsx
  src/components/settings/tabs/generalTab.tsx
  ```

- **Import Style:**  
  Use **relative imports** within the codebase.  
  _Example:_  
  ```typescript
  import { getSetting } from "../utils/settings";
  import PluginComponent from "./components/PluginComponent";
  ```

- **Export Style:**  
  Use **named exports** for modules and components.  
  _Example:_  
  ```typescript
  export function activatePlugin() { ... }
  export const PLUGIN_ID = "myPlugin";
  ```

- **Commit Messages:**  
  - Freeform, sometimes prefixed (e.g., `settings:`, `translate:`, `reviewdb:`).
  - Keep messages concise and reference the area or plugin affected.
  - _Example:_  
    ```
    settings: add dark mode toggle to general tab
    translate: update Spanish translations
    ```

## Workflows

### Plugin Bugfix or Update
**Trigger:** When you need to fix a bug or update functionality in an existing plugin  
**Command:** `/fix-plugin`

1. Identify the plugin(s) that need a bugfix or update.
2. Edit the plugin's main file (`index.tsx` or `index.ts`).
3. Optionally update related component or utility files within the plugin folder.
4. Commit with a message referencing the plugin(s) and the fix.

_Example commit:_  
```
Better error handling in src/plugins/myPlugin/index.tsx
```

### Add New Plugin
**Trigger:** When you want to add a new plugin to Vencord  
**Command:** `/new-plugin`

1. Create a new folder under `src/plugins` (e.g., `src/plugins/myNewPlugin`).
2. Add the main plugin file (`index.ts` or `index.tsx`).
3. Update `src/utils/constants.ts` to register the new plugin.
4. Commit with a message referencing the new plugin.

_Example file structure:_  
```
src/plugins/myNewPlugin/index.tsx
src/utils/constants.ts
```

### Settings UI Enhancement
**Trigger:** When you want to add, fix, or enhance settings UI elements  
**Command:** `/update-settings-ui`

1. Edit settings tab/component files (e.g., `src/components/settings/tabs/generalTab.tsx`).
2. Optionally update related plugin settings files (e.g., `src/plugins/_core/settings.tsx`).
3. Commit with a message referencing the settings changes.

_Example:_  
```
settings: improve accessibility in generalTab.tsx
```

### Plugin Settings Removal or Refactor
**Trigger:** When you need to deprecate or refactor a plugin option/setting across the codebase  
**Command:** `/refactor-plugin-settings`

1. Identify the deprecated or refactored field.
2. Edit all affected plugin files to remove or update the field.
3. Edit shared settings components and types (e.g., `src/utils/types.ts`).
4. Commit with a message referencing the field removal or refactor.

_Example:_  
```
Remove deprecated 'enableBeta' setting from all plugins
```

### Version Bump Release
**Trigger:** When you want to release a new version of Vencord  
**Command:** `/bump-version`

1. Update the version number in `package.json`.
2. Optionally update `src/plugins/vencordToolbox/index.tsx` or similar if needed.
3. Commit with the version number as the message.

_Example:_  
```
v1.8.0
```

### Modal UI Refactor or Migration
**Trigger:** When you want to update modal implementation or migrate to a new modal system  
**Command:** `/refactor-modals`

1. Edit or add modal component files in core and plugins (e.g., `*Modal*.tsx`).
2. Update related CSS and type definitions (e.g., `Modal.d.ts`).
3. Commit with a message referencing modal migration or refactor.

_Example:_  
```
Refactor all plugin modals to use new modal system
```

## Testing Patterns

- **Test File Naming:**  
  Test files follow the pattern `*.test.*` (e.g., `myPlugin.test.ts`).
- **Framework:**  
  The testing framework is not explicitly detected, but tests are colocated with source files or in dedicated test files.
- **Example Test File:**  
  ```
  src/plugins/myPlugin/myPlugin.test.ts
  ```

## Commands

| Command                | Purpose                                                      |
|------------------------|--------------------------------------------------------------|
| /fix-plugin            | Fix or update an existing plugin                             |
| /new-plugin            | Add a new plugin                                             |
| /update-settings-ui    | Enhance or fix the settings UI                               |
| /refactor-plugin-settings | Remove or refactor a plugin setting across the codebase   |
| /bump-version          | Bump the version for a new release                           |
| /refactor-modals       | Refactor or migrate modal UI components                      |
```
