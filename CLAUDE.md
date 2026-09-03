# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project state

`my-playground` is a scratch directory, not yet a real project. It currently holds a single
static page, `index.html`, with no build system, dependencies, tests, or version control.

There is no package manager, no toolchain, and no test runner. Do not assume `npm`, `pnpm`,
or any framework is available — check before reaching for one.

## Running

`index.html` is fully self-contained (inline `<style>`, no external assets), so it runs by
opening the file directly:

```bash
open index.html
```

If a task needs a real HTTP origin (fetch, modules, service workers), serve the directory
rather than adding a dependency:

```bash
python3 -m http.server 8000
```

## Conventions

Keep `index.html` self-contained unless the task calls for splitting assets out. It styles
both light and dark via `prefers-color-scheme` and `color-scheme: light dark` — preserve
that pairing when changing colors, so the page does not go light-on-light in dark mode.

## When this grows

This directory is a playground: it is expected to gain structure. When adding a build step,
dependency manager, or test runner, replace the sections above with the real commands rather
than layering new instructions on top of these placeholders.
