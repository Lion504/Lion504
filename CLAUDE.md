# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository purpose

This is `Lion504/Lion504` — a GitHub **profile README repo**. Its special name matches the account owner's username, which makes GitHub render `README.md` directly on the user's profile page (https://github.com/Lion504). There is no application code, build system, package manifest, or test suite here — the entire "product" is the rendered README.

## Structure

- `README.md` — the profile page content. Markdown with embedded HTML tables/badges (shields.io) for layout.
- `github-metrics.svg` — auto-generated stats image embedded in the README (`![Metrics](.../github-metrics.svg)`). Do not hand-edit this file; it is overwritten by the workflow below.
- `.github/workflows/metrics.yml` — regenerates `github-metrics.svg` using `lowlighter/metrics@latest`, committing the result back to `main`. Runs daily (`cron: "0 0 * * *"`), on manual dispatch, and on every push to `main`.

## Working conventions

- Edits here are content edits to `README.md`, not code changes — there's nothing to compile, lint, or test.
- Keep the shields.io badge style consistent with existing entries when adding a new skill/tool badge (`https://img.shields.io/badge/-<Label>-<hex>?style=flat-square&logo=<logo>&logoColor=<color>`).
- The "Featured Projects" table links to other Lion504 repos (`Fi-Job-Maps`, `Junc25`, `CLboost`, `JobAio`) — statuses there may drift from those projects' actual state, so verify before updating claims if asked.
- Don't manually edit `github-metrics.svg`; if it looks stale, the fix is re-running the `Metrics` workflow, not editing the file.
- The metrics workflow needs a `METRICS_TOKEN` secret configured in the repo settings — it's not something to add via code changes.
