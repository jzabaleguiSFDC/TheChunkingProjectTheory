# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Purpose

This repository documents an original theory ("The Chunking Project Theory") in prose first, then renders it as a standalone HTML slide deck. There is no build system or application code — the deliverables are a written source of truth and a presentation generated from it.

The work happens in two phases, in order:

1. **Document the theory** — capture the theory as structured Markdown. This is the canonical source. Get it complete and correct before touching the deck.
2. **Generate the HTML deck** — derive a self-contained `.html` presentation from the documented theory. The deck is a *view* of the docs, never the source of truth.

When editing, always update the Markdown source first; regenerate or update the deck from it. Never let the deck drift ahead of the docs.

## Conventions

- **Single source of truth**: the theory lives in Markdown. The HTML deck is generated output. If they disagree, the Markdown wins.
- **Self-contained deck**: the HTML deck must open directly in a browser with no server, build step, or network fetch — inline all CSS/JS, no external CDN dependencies. It should be shareable as one file.
- **Preserve the author's claims verbatim**: this is the user's own theory. Do not soften, "correct", or invent claims. When something is unclear or a gap exists, ask rather than fill it in.
- **Spanish is the working language** for discussion; written docs/deck language follows the user's lead per artifact.

## Structure (as it develops)

The folder is currently empty. Expected layout as content lands:

- Theory documentation in Markdown (the source of truth).
- A generated self-contained HTML deck derived from that documentation.

## Previewing the deck

The deck is a static file — open it directly, or serve the folder if a local URL is preferred:

```bash
open <deck>.html                 # macOS: open in default browser
python3 -m http.server 8000      # then visit http://localhost:8000
```
