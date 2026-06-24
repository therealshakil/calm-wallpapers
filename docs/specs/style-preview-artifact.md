# Spec — Style preview artifact

**Status:** draft · **Date:** 2026-06-24 · **App:** calm-wallpapers · **Kind:** capability (not an artwork)

A self-contained HTML page that previews a calm style — its palette, texture, composition, and example
prompt — as one glanceable "style board". Rendered live via the Artifact tool and committed to the repo.

## Why

A style can't be *seen* until its wallpapers exist, and the wallpapers are made by hand in Midjourney
(slow, yours). A style board lets you preview and iterate the *direction* — palette, composition,
texture — before and around the making. It also serves the suite's "screenshots are calm / show, don't
tell" instinct: a quiet picture lands faster than paragraphs. Serves Article I (glanceable, finite) and
VI (calm by construction).

## What it does

One quiet page per style. Glanceable, read-only, nothing to operate.

- **Happy:** shows the style's palette as swatches (with hexes + roles), a plain-language texture note, a
  composition sketch, and the example prompt — light and dark shown together, not as an operable toggle.
- **Quiet & empty:** a style with no wallpapers yet still has a meaningful board (palette + intent are
  enough). Empty of real imagery is a first-class state, not a gap.
- **When it fails:** if a sketch or embed looks wrong, it's a static file — fix and re-render; nothing
  breaks, nothing alarms.

## Not this (non-goals)

Not a gallery, website, or growing index. Not an interactive app (no operation beyond glancing). Not a
generator. Not a substitute for the real wallpaper files (those stay PNGs in `wallpapers/`). No external
assets, no analytics. One preview per style — finite.

## Research

Proportionate (a tooling call, low bar; reasoned, not heavily sourced):

- **Artifact constraints (hard):** a strict CSP blocks all external hosts — so the page must be
  **self-contained**: inline CSS, no external fonts/scripts/CDN, any image embedded as a `data:` URI.
  Build with the `artifact-design` skill loaded.
- **Calm placeholders:** until real wallpapers exist, a CSS/SVG composition sketch is fine **only if
  labelled a sketch, not the artwork** (suite identity: placeholders are named as placeholders).
- Ties to `Calm.md` seed "Screenshots are calm" (show, don't tell).

## How (the plan)

- **One file per style:** `docs/specs/<style>/preview.html` (e.g. `sakina/preview.html`).
- **Self-contained HTML**, calm by construction: the style's own palette tokens; generous whitespace; low
  contrast; no `!` or alarm; **almost no motion**, `prefers-reduced-motion` honoured (and near-default
  anyway); light + dark shown side by side.
- **Render + iterate** with the Artifact tool (live preview on claude.ai); **commit the file** so the
  board lives in the repo and travels with the style.
- **Real wallpapers, once made,** can be embedded as `data:` URIs (or the board can simply name them);
  the sketch is replaced by the real thing.

## Open questions

- Composition sketch: CSS/SVG approximation, or leave composition to words until a real image exists?
- One board per style, or could a board hold a style's several artworks once they exist?

## Tasks

Filled at build time:
- [ ] Build `sakina/preview.html` (palette swatches, texture note, composition sketch, prompt;
  light + dark).
- [ ] Render via Artifact, iterate, commit the file.
- [ ] Repeat the pattern for `ink-peanuts` when wanted.

## Constitution Check

1. **Serves:** I (glanceable, finite — a board to glance at, one per style), VI (calm visual,
   `prefers-reduced-motion`, no alarm), VIII (a board, not a website — subtract), IX (self-contained, no
   external deps, no fragile pipeline).
2. **Violates:** none — read-only, static, no engagement mechanics or data collection; confirmed vs
   Articles + banned patterns. The artifact previews a style; it is not the wallpaper.
3. **Subtracts:** previews the *direction* instead of needing the finished images first; one finite file
   per style, not a gallery that grows.
4. **Calm:** the empty (no-images-yet) state is first-class; placeholders are honestly labelled; no
   motion to honour `prefers-reduced-motion` against; happy and empty paths both specified.
