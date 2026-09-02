---
name: github-first
description: Use whenever any task involves interacting with GitHub (repos, issues, PRs, gists, releases, CI, code search on GitHub). Enforces using the `gh` CLI immediately, before any other tool, library, or API.
---

# GitHub First

Any time a task needs to interact with GitHub, use the `gh` CLI **immediately and before anything else**.

## Rules

1. **`gh` is the first move.** The moment a task mentions GitHub — repos, issues, pull requests, gists, releases, actions, or searching GitHub-hosted code — run `gh` before considering any other approach.
2. **Do not reach for alternatives first.** Never start with raw `curl` to api.github.com, git clones over the API, web fetches of github.com pages, or installing/writing scripts or libraries. `gh` comes first; only fall back to something else if `gh` genuinely cannot do the job (and say why).
3. **Check auth once when needed.** If a `gh` command fails with an auth error, run `gh auth status` and report the problem to the user — do not silently switch to a different method.
4. **Prefer targeted subcommands.** Use the most specific `gh` subcommand available:
   - Repos / files: `gh repo view`, `gh repo clone`, `gh api`
   - Issues: `gh issue list`, `gh issue view`, `gh issue create`, `gh issue edit`, `gh issue close`
   - Pull requests: `gh pr list`, `gh pr view`, `gh pr create`, `gh pr checkout`, `gh pr merge`
   - Runs / CI: `gh run list`, `gh run view`, `gh run watch`
   - Gists: `gh gist create`, `gh gist view`
   - Searching GitHub: `gh search code|issues|prs|repos`
5. **Keep output parseable.** Use `--json` with `--jq` (or `-t` for templates) when results feed into further steps.
