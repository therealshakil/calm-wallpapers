# Style — Sakina

**Status:** ready · locked 2026-06-24 (abstract-only; `--sref` bound) · **Date:** 2026-06-24 · **The second calm style.** *Sakina*
(سكينة) — the calm that settles. Named for the energy, not a place or a faith.

The energy, not the depiction. A style is **Layer B** of the [prompt ladder](../../prompt-ladder.md):
the register and motif vocabulary that arrive on the upper rungs, once the universal calm base (Layer A)
is set. Grounded in [research.md](../../research.md), "What is Islamic calm?".

## The register

**Sakina** (*sakīna*, سكينة) is **a stillness that feels received, not achieved** — the tranquility that
descends and settles on the heart (Qur'an 48:4); with it, the quiet of a heart at rest (*ṭumaʾnīna*). The
style is named for that calm — the energy, not the depiction. Its visual expression turns *away* from
depicting things and *toward* unity and the unrepresentable (*tawḥīd*), so it is **non-figurative by
nature**, which sits cleanly inside the calm base.

The calm doesn't come from a subject; it comes from **no focal point.** The pattern continues past the
frame, weight is even everywhere, and the eye never locks — it drifts and rests at once. Add deep
symmetry with gentle variation (unity in multiplicity), flowing line (the breath/living counterpart to
fixed geometry), generous void, and soft light (*nūr*) instead of hard contrast.

*(Held honestly: the Qur'anic vocabulary is canonical; reading deliberate theology into pattern is the
perennialist interpretation — Burckhardt, Nasr — with Grabar as the cautious counter-voice. We borrow
the energy, not a claim about intent.)*

## Palette — calm colour (a chosen departure)

Colour is allowed here under calm-wallpapers' **colour principle** ([charter](../../charter.md) §3: calm
+ research-earned) — this is the first style to use it. It departs from the suite's monochrome identity —
a documented repo stance, not drift, proposed to identity.md (the person locks); [research](../../research.md)
backs the *calm* of this palette. The governing rule: **calm colour = low saturation + light value + low
contrast** — a neutral ground dominating, accents sparse and muted (saturation, not hue, is the arousal
lever).

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

## Composition — abstract pattern, no subject

**Abstract and non-representational — no subjects, no objects, no flowers.** The geometry itself is the
whole image. This adjusts Layer A's "one small subject in a void": here the *field of geometry* is the
subject, so:

- **Pure geometry** — flat, 2D, line-based tessellation. Never a depicted thing (no vase, bouquet, still
  life, fruit, or wall-scene).
- **Large-scale and low-density** — open, not a dense rug. The calm is in the breathing room.
- **Dissolves into void** — a medallion or edge-band fading to empty ground; the screen stays open, the
  gaze unfixed.
- **No focal point** — even weight; nothing begins or ends inside the frame.

## Motif vocabulary

Abstract geometric structures only — never objects. A starting list — it firms up as artworks land:

- interlacing **eight-point star geometry** (*girih*) · polygon-and-star **tessellation**
- **strapwork** — interlaced ribbon lines, over-and-under
- a **medallion** of geometry dissolving into void · an **edge-band** fading to empty ground
- a soft **inner glow of light** (*nūr*) within an open field

**No arabesque / vegetal line.** It reads as flowers — *islīmī* is stylised plants, and Midjourney renders
it as literal botanicals. Sakina is **pure geometry**. And **describe the geometry directly — never the
word "Islamic"** (it pulls clichés: flowers, gold, domes, fake script).

## Hard exclusions

For accuracy and respect, on top of the base `--no` list:

- **No subjects or objects** — no flowers, bouquet, vase, fruit, still life, plants, leaves, botanical,
  buildings, walls-as-scenes. Abstract and non-representational only. Negative-prompt `flowers, floral,
  bouquet, vase, fruit, still life, plants, leaves, botanical, objects, representational, realistic, 3d,
  photographic`.
- **No Arabic / calligraphy / pseudo-script** — Midjourney can't render real Arabic; faked scripture is
  worse than ugly (research.md). Negative-prompt `text, arabic, calligraphy, letters, words, script`.
- **No figures, no faces.** No **literal mosque scenes** (domes, minarets) — pure pattern, line, light.

## The style's prompt fragment

Drop onto the Layer A base (see [recipe](../../recipe.md) for full parameters):

```
... abstract geometric pattern, seamless tessellation of interlocking eight-pointed stars and polygons,
flat two-dimensional line work, non-representational, minimal, limewashed cream and warm sand ground with
one dusty desaturated indigo line, matte, low saturation, low contrast, soft diffuse light, low density,
dissolving into generous empty space, no focal point, even rhythmic symmetry, calm and still ...
--no flowers, floral, bouquet, vase, fruit, still life, plants, leaves, botanical, objects, people, figures, representational, realistic, photo, 3d, glossy, sheen, vivid, saturated, neon, jewel tones, gold, gilded, high contrast, dark heavy background, busy, ornate, muqarnas, text, arabic, calligraphy, letters, mosque, dome, minaret, focal point, centred motif
```

## Midjourney binding

How this style maps to Midjourney — see the [ladder](../../prompt-ladder.md), "How a style maps to
Midjourney". To set once a first anchor is chosen **by hand**:

- **Anchor image:** `./anchor.png` — _to add_ (download a honed tile here; the source of truth if the
  code ever drifts).
- **`--sref`:** `5152366415` — locked 2026-06-24, from the Style Creator session.
- **`--sw`:** `100` — style weight; lower it if the look pulls too hard.
- **`--v`:** `8.1` — the model the style was honed on.

### Style settings guidance

Pin the whole config so the style reproduces itself — consistency is calm. Change only the subject and the
device `--ar`; never touch the knobs.

| Setting | Value | Why |
|---|---|---|
| Version | `--v 8.1` | the model the look was built on |
| Variety / chaos | `--c 0` | **low — the biggest consistency lever**; high variety makes every render diverge |
| Weirdness | `0` | no oddness |
| Style weight | `--sw 100` | steady pull from the anchor |
| `--sref` | `5152366415` | the look every artwork shares |

Two dials are *taste, not consistency* — set each once to the look you keep, then pin it and don't move it:

- **Mode:** Raw (flat, matte, less auto-saturated — the calmer default) **or** Standard (softer, more
  painterly — the look from the first liked renders).
- **Stylize (`--s`):** low (`--s 50`) for faithful and flat; higher for painterly. Pick, pin, leave.

Predictability is the point: once these are set, a Sakina render is repeatable — that *is* the calm.

## Artworks in this style

| # | Artwork | Status |
|---|---|---|
| 001 | [Star lattice](./001-star-lattice.md) | draft |

---

## Constitution Check

1. **Serves:** the suite's calm register (low-arousal, low-contrast — colour a documented departure, see
   Palette), VI (no focal point, soft glow over hard contrast — calm by construction), I (a bounded motif
   vocabulary, room to breathe), and the *energy-not-depiction* reading of the tradition.
2. **Violates:** the suite's monochrome rule — *deliberately*, by the person's choice, recorded as an
   exception to be reflected to identity.md (not drift), and held calm by the low-saturation/light/low-
   contrast rule (research-backed). Otherwise none — non-figurative, no text/calligraphy/figures; the hard
   exclusions hold the respect and the calm.
3. **Subtracts:** one register + a finite motif list + hard exclusions keep the set coherent, respectful,
   and small — fewer decisions per artwork.
4. **Calm:** the no-focal-point field is restful by design; happy and quiet paths inherit from the
   [ladder](../../prompt-ladder.md); an off-brand or filtered generation is discarded, never chased.
