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

## Palette — calm colour (a chosen departure)

This style **deliberately departs from the suite's locked monochrome identity** — colour is allowed here,
by choice, recorded as an exception, not drift (the person's call; [research](../../research.md) backs the
*calm* of it). The governing rule: **calm colour = low saturation + light value + low contrast** — a
neutral ground dominating, accents sparse and muted (saturation, not hue, is the arousal lever).

Blends the Alhambra's cool geometric restraint with the Swahili coast's warm earthiness:

| Role | Name | Hex | Share |
|---|---|---|---|
| Ground | Lime-Wash | `#EDE6D6` | ~70% |
| Secondary ground | Warm Sand | `#DAC9A6` | ~15% |
| Accent | Dusty Indigo | `#5E7287` | ~6% |
| Accent | Muted Sage | `#8A9A82` | ~5% |
| Accent (sparse) | Soft Terracotta | `#B07A5E` | ~3% |
| Line only | Faded Ink | `#4A4A45` | ~1% |

- **One accent leads** per piece; all at once reads busy. Default: Lime-Wash + Dusty Indigo, faint Muted
  Sage second. Indian-Ocean **Muted Teal `#6E9C99`** is an optional swap for the indigo.
- **No gold, no gloss, no pure-black or dark-heavy field** — dark muted tones still read arousing, so keep
  values light-to-mid. *Dark variant:* a soft deep-taupe ground, not near-black, accents even quieter.
- Hexes are calibrated starting points, not measured — tune by eye.
- *To reflect to the suite:* this proposes calm-wallpapers may use calm colour for this style — an
  exception to identity.md's "no colour", your lock.

## Texture — matte, weathered, a quiet ground

Texture is an all-over ground, never a subject (no focal point). Evoke the **matte** side of each
tradition:

- **Matte carved plaster, low relief** (Alhambra *yesería*) — chalky, non-reflective, soft self-shadow.
- **Limewashed coral wall** (Swahili) — weathered, sun-bleached cream/sand, gently porous.
- **Soft hand-pressed / near-matte plaster** — seamless, faint wabi-sabi grain.
- Optional **fine woven palm tooth** (*mkeka*) — a subtle all-over grain, like paper tooth.

Hold to: matte over glossy, shallow over deep relief, diffuse light over dramatic, even all-over, low
contrast. Avoid glaze/sheen, gilded **muqarnas**, deep-carved doors — the busy ends.

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
... large-scale interlacing eight-point star geometry (girih), fine low relief in matte carved plaster,
limewashed cream and warm sand ground, one dusty desaturated indigo accent, low saturation, low contrast,
soft diffuse light, sun-bleached and chalky, low density, dissolving softly into generous empty space, no
focal point, even rhythmic symmetry, calm and still ...
--no gold, gilded, metallic, glossy, glaze, sheen, reflective, vivid, saturated, neon, jewel tones, high contrast, dark heavy background, kanga textile, busy, ornate, muqarnas, carved door, text, arabic, calligraphy, letters, words, script, mosque, dome, minaret, figures, faces, focal point, centred motif
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
| 001 | [Star lattice](./001-star-lattice.md) | draft |

---

## Constitution Check

1. **Serves:** the suite identity (monochrome, low-arousal), VI (no focal point, soft glow over hard
   contrast — calm by construction), I (a bounded motif vocabulary, room to breathe), and the
   *energy-not-depiction* reading of the tradition.
2. **Violates:** the suite's monochrome rule — *deliberately*, by the person's choice, recorded as an
   exception to be reflected to identity.md (not drift), and held calm by the low-saturation/light/low-
   contrast rule (research-backed). Otherwise none — non-figurative, no text/calligraphy/figures; the hard
   exclusions hold the respect and the calm.
3. **Subtracts:** one register + a finite motif list + hard exclusions keep the set coherent, respectful,
   and small — fewer decisions per artwork.
4. **Calm:** the no-focal-point field is restful by design; happy and quiet paths inherit from the
   [ladder](../../prompt-ladder.md); an off-brand or filtered generation is discarded, never chased.
