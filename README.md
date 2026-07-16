# The Chunking Project Theory

A theory on why AI does **not** let project-implementation firms compress a 1-year project into a month — and what actually happens instead.

**Core claim:** the critical path is set by *dependencies on the client*, not by the implementer's speed. AI accelerates the implementer's side of each work unit (a *chunk*), but the client may not be able to give feedback, hold meetings and verbalize requirements at the new pace. So either you shrink the team and keep the chunk size, or the compression is impossible.

## Contents

- **`teoria-del-chunking.md`** — the theory, written out (source of truth).
- **`intro.html`** — self-contained hand-drawn "doodle" animation introducing the theory, with narration (Web Speech API).
- **`chunk-definition.html`** — second animation: the anatomy of a chunk (entry gate → internal work → exit gate) and why AI shrinks the boxes but not the gates.
- **`salesforce-fit.html`** — third animation: where the theory lands inside Salesforce — SEAP (shrinks many boxes), AI Delivery (the default: acceleration becomes more scope or quality, not less time), and Quantum Leap (the only lever that moves the gates — via contractual speed commitments on both sides).

Each `.html` opens in a browser — no build step, no server, no network.

## Viewing the animations

Open a file directly:

```bash
open intro.html
open chunk-definition.html
open salesforce-fit.html
```

Click once to start (browsers require a gesture before playing audio).
Controls: `space` play/pause · `←/→` scene · `M` mute · `R` replay.
