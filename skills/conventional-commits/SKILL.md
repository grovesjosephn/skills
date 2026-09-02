---
name: conventional-commits
description: Write git commit messages using the Conventional Commits specification. Use whenever creating, writing, or drafting git commit messages, including commits made with git CLI or gh.
---

# Conventional Commits

Always write git commit messages following the [Conventional Commits 1.0.0](https://www.conventionalcommits.org/en/v1.0.0/) specification.

## Format

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

## Rules

1. **Type is mandatory.** One of:
   - `feat` — new feature
   - `fix` — bug fix
   - `docs` — documentation only
   - `style` — formatting, no code meaning change
   - `refactor` — code change that is neither feature nor fix
   - `perf` — performance improvement
   - `test` — adding or correcting tests
   - `build` — build system or dependency changes
   - `ci` — CI configuration changes
   - `chore` — maintenance that doesn't fit other types
   - `revert` — reverting a previous commit
2. **Scope is optional.** Use when the change is contained to one area, e.g. `feat(obsidian-cli):`, `fix(parser):`.
3. **Description is imperative, lowercase, no period.** "add skill" not "added skill." Summarize the change in 72 characters or fewer.
4. **Breaking changes** must be flagged: `!` after the type/scope (e.g. `feat!:`) and/or a `BREAKING CHANGE:` footer describing what broke.
5. **Body** (optional) explains *what* and *why*, not *how*. Wrap at 72 characters, separated from the subject by a blank line.
6. **Footers** for issue references (`Closes #123`) and metadata (`Reviewed-by: ...`).
7. **Never** use non-conventional messages like "update", "changes", "misc fixes", or "wip".

## Examples

```
feat: add conventional-commits skill

fix(api): handle timeout on long-running requests

Closes #42

refactor!: rename skills/<name> layout to skills/<category>/<name>

BREAKING CHANGE: skill paths no longer resolve at the old locations.
```
