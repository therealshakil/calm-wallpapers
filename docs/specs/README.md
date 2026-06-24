# Specs — calm-wallpapers

In this project, **each artwork is a spec**, grouped under a **calm style**. A style folder holds its
own `STYLE.md` (the art direction) and its numbered artwork specs. The shared *method* — the
[recipe](../recipe.md) and the [prompt ladder](../prompt-ladder.md) — lives a level up and serves every
style. Each spec is backed by [research.md](../research.md) and ends in the Constitution Check.
Co-authored; only the person marks one *ready*.

## Styles

| Style | Art direction | Status |
|---|---|---|
| [ink on paper, Peanuts](./ink-peanuts/STYLE.md) | warm ink, Peanuts + poetry; the first style | draft |
| [Sakina](./sakina/STYLE.md) | سكينة, the calm that settles — the energy not the depiction; Alhambra × Swahili coast geometry, no focal point, matte plaster, calm desaturated colour | ready |

## Capability specs

Cross-cutting specs (not artworks): how the repo builds things.

| Spec | What | Status |
|---|---|---|
| [Style preview artifact](./style-preview-artifact.md) | a glanceable HTML style board, committed + rendered via the Artifact tool | draft |

## Layout

```
docs/
  recipe.md            how: the look + parameters
  prompt-ladder.md     how: the 4-layer process + per-device targets
  specs/
    ink-peanuts/
      STYLE.md         the style's art direction (Layer B)
      001-crescent-moon.md   an artwork (Layer C + D)
    <next-style>/
      STYLE.md
      ...
```

Rough, un-promoted thoughts live in [spec-ideas.md](./spec-ideas.md).
