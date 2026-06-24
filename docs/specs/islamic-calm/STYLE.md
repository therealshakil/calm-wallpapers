# Style — Islamic calm

**Status:** draft · **Date:** 2026-06-24 · **The second calm style.**

The energy, not the depiction. A style is **Layer B** of the [prompt ladder](../../prompt-ladder.md):
the register and motif vocabulary that arrive on the upper rungs, once the universal calm base (Layer A)
is set. Grounded in [research.md](../../research.md), "What is Islamic calm?".

## The register

Islamic calm is **a stillness that feels received, not achieved** — peace that settles on the heart
(*sakīna*), the quiet of a heart at rest (*ṭumaʾnīna*). Its visual expression turns *away* from depicting
things and *toward* unity and the unrepresentable (*tawḥīd*) — so this style is **non-figurative by
nature**, which sits cleanly inside the calm base.

The calm doesn't come from a subject; it comes from **no focal point.** The pattern continues past the
frame, weight is even everywhere, and the eye never locks — it drifts and rests at once. Add deep
symmetry with gentle variation (unity in multiplicity), flowing line (the breath/living counterpart to
fixed geometry), generous void, and soft light (*nūr*) instead of hard contrast.

*(Held honestly: the Qur'anic vocabulary is canonical; reading deliberate theology into pattern is the
perennialist interpretation — Burckhardt, Nasr — with Grabar as the cautious counter-voice. We borrow
the energy, not a claim about intent.)*

## Palette

**Monochrome**, within the suite [identity](https://github.com/shakilclark/calm/blob/main/docs/identity.md):
charcoal/grey line on warm off-white (light) / bone-white line on soft off-black (dark). *Nūr* (light) is
carried by a soft tonal glow, not by colour. A single calm hue would be a deliberate amendment to the
monochrome rule — parked as a later choice, not assumed here.

## Composition — the pattern *is* the subject

This style adjusts Layer A's "one small subject in a void". Here the field of pattern is the subject, so:

- **Large-scale and low-density** — open, not a dense rug. The calm is in the breathing room.
- **Occupies part of the frame and dissolves into void** — a medallion or edge-band fading to empty
  paper, keeping the screen open (room for icons) and the gaze unfixed.
- **No focal point** — even weight; nothing begins or ends inside the frame.

## Motif vocabulary

Non-figurative structures, not objects. A starting list — it firms up as artworks land:

- interlacing **eight-point star geometry** (*girih*) · polygon-and-star tessellation
- a **medallion** dissolving outward into void · an **edge-band** of pattern fading to empty paper
- flowing **arabesque vegetal line** (*islīmī*) · a single continuous interlaced line
- a soft **inner glow of light** (*nūr*) within an open field

**Describe the geometry and the energy directly — never the word "Islamic"** (it pulls Midjourney toward
clichés: domes, gold, fake script).

## Hard exclusions

For accuracy and respect, on top of the base `--no` list:

- **No Arabic / calligraphy / pseudo-script** — Midjourney can't render real Arabic; faked scripture is
  worse than ugly (research.md). Negative-prompt `text, arabic, calligraphy, letters, words, script`.
- **No figures, no faces.** No **literal mosque scenes** (domes, minarets) — pure pattern, line, light.

## The style's prompt fragment

Drop onto the Layer A base (see [recipe](../../recipe.md) for full parameters):

```
... large-scale interlacing eight-point star geometry (girih), fine hand-drawn ink line, low density,
occupying part of the frame and dissolving softly into generous empty space, no focal point, even
rhythmic symmetry, a soft inner glow of light, calm and still ...
--no text, arabic, calligraphy, letters, words, script, mosque, dome, minaret, figures, faces, high contrast, dense clutter
```

## Midjourney binding

How this style maps to Midjourney — see the [ladder](../../prompt-ladder.md), "How a style maps to
Midjourney". To set once a first anchor is chosen **by hand**:

- **Anchor image:** `./anchor.png` — _to add_ (the source of truth; the look every artwork shares).
- **`--sref`:** _to set_ — the style code derived from the anchor (make it in a finite Style Creator
  session — see the [ladder](../../prompt-ladder.md), "Making a style's code").
- **`--sw`:** `100` — style weight; lower it if the look pulls too hard.
- **`--sv` / `--v`:** _to record_ — sref version + the MJ model version this was made on.

## Artworks in this style

| # | Artwork | Status |
|---|---|---|
| — | _none yet_ | — |

---

## Constitution Check

1. **Serves:** the suite identity (monochrome, low-arousal), VI (no focal point, soft glow over hard
   contrast — calm by construction), I (a bounded motif vocabulary, room to breathe), and the
   *energy-not-depiction* reading of the tradition.
2. **Violates:** none — non-figurative, monochrome, no text/calligraphy/figures (the hard exclusions hold
   the respect and the calm); confirmed vs Articles + banned patterns. Palette stays monochrome, so no
   identity amendment is invoked.
3. **Subtracts:** one register + a finite motif list + hard exclusions keep the set coherent, respectful,
   and small — fewer decisions per artwork.
4. **Calm:** the no-focal-point field is restful by design; happy and quiet paths inherit from the
   [ladder](../../prompt-ladder.md); an off-brand or filtered generation is discarded, never chased.
