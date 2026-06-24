# Working calm — calm-wallpapers

This repo holds a small, curated set of desktop wallpapers, made by hand in Midjourney.
It is the first thing built the calm way *outside* the home repo — a project that **adds calm to
itself** by inheriting direction rather than re-deriving it.

## Governing law lives elsewhere

This repo does not restate the rules. It inherits them from the calm suite:

- **`github.com/shakilclark/calm`** — read it as the upstream:
  - `CONSTITUTION.md` — the ten Articles + banned patterns. Supreme.
  - `docs/identity.md` — the look: monochrome ink on paper, Peanuts-gentle, almost no motion.
  - `docs/calm-language.md` — the voice.
  - `CLAUDE.md` — how to *be* while you build.

When a choice here conflicts with the calm Constitution, the choice loses — not the Constitution.
Everything in `docs/` answers to it, and the docs that make a claim end with the four-line
Constitution Check.

## How to "add calm to a project"

This file is the whole mechanism. To calm any project: drop in a short `CLAUDE.md` that names
`shakilclark/calm` as governing law and points at the four files above. No template to install, no
machinery to maintain — the calm repo is written to be read by a person or an assistant, so adopting
it is just pointing at it. That is the pattern; this repo is the first to use it.

## What's specific here

- **The making is hands-on, and that's the point.** A person uses Midjourney by hand — see
  [`docs/the-midjourney-exception.md`](./docs/the-midjourney-exception.md) for why that's calm even
  though the suite's identity says "not Midjourney" for *automated* generation.
- **The recipe, not the pipeline.** [`docs/recipe.md`](./docs/recipe.md) is the craft doc: how to
  prompt for the calm look, the parameters and why, and how to keep a set consistent. It is run by a
  human, never by a script.
- **Mechanics for any assistant working here:** absolute paths and tool dir-flags (`git -C`), never
  `cd`; one operation per command; no chained or substituted commands. Push after every commit. These
  carry over from the suite's `CLAUDE.md`.
