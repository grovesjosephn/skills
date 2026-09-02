---
name: obsidian-development
description: Develop and debug Obsidian plugins and themes using the Obsidian CLI. Covers the reload/verify develop-test cycle, error checking, screenshots, DOM and CSS inspection, and running JavaScript in the app context. Use when building, changing, testing, or debugging an Obsidian plugin or theme. For general vault interaction, use the obsidian-cli skill instead.
---

# Obsidian Development

Use the `obsidian` CLI to develop and debug Obsidian plugins and themes. Requires Obsidian to be open with the plugin or theme in the vault. For general CLI syntax, file/vault targeting, and note operations, see the obsidian-cli skill.

## Command reference

Run `obsidian help` to see all available commands, including additional developer commands for CDP and debugger controls. This is always up to date. Full docs: https://help.obsidian.md/cli

## Develop/test cycle

After making code changes to a plugin or theme, follow this workflow:

1. **Reload** the plugin to pick up changes:
   ```bash
   obsidian plugin:reload id=my-plugin
   ```
2. **Check for errors** — if errors appear, fix and repeat from step 1:
   ```bash
   obsidian dev:errors
   ```
3. **Verify visually** with a screenshot or DOM inspection:
   ```bash
   obsidian dev:screenshot path=screenshot.png
   obsidian dev:dom selector=".workspace-leaf" text
   ```
4. **Check console output** for warnings or unexpected logs:
   ```bash
   obsidian dev:console level=error
   ```

## Additional developer commands

Run JavaScript in the app context:

```bash
obsidian eval code="app.vault.getFiles().length"
```

Inspect CSS values:

```bash
obsidian dev:css selector=".workspace-leaf" prop=background-color
```

Toggle mobile emulation:

```bash
obsidian dev:mobile on
```
