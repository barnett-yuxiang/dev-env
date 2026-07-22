# Codex Plugin Documentation Design

## Goal

Keep Codex personalization instructions focused while documenting the small set of Codex plugins that are currently useful in this environment.

## Scope

- Add `tools/codex/plugins.md` as the dedicated plugin reference.
- Document Superpowers, Metabase, Data Analytics, and Chrome.
- Add a relative link from `tools/codex/codex.md` to the plugin reference.
- Fix the three image paths in `tools/git-tool/git-tool.md` so they resolve to `tools/assets/`.
- Leave `.gitignore` and all `zshrc.private` files unchanged.

## Content Structure

`tools/codex/plugins.md` will use a compact table with one row per plugin. Each row will state the plugin name, its main use cases, and why it is useful. Versions will not be recorded because installed plugin versions change independently of this repository.

`tools/codex/codex.md` will retain the existing Personalization section and add a short References section linking to `plugins.md`.

## Verification

- Confirm all four requested plugins appear exactly once in the plugin reference.
- Resolve every local Markdown link and image path to an existing repository file.
- Confirm `.gitignore` and the tracked state of `zshrc.private` files are unchanged.
- Run `git diff --check` and inspect the final diff.
