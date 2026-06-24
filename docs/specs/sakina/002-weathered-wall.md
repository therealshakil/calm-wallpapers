# Artwork 002 — Weathered wall *(working title — name at the end)*

**Status:** draft · **Date:** 2026-06-24 · **Style:** [Sakina](./STYLE.md)

The feeling, texture, and colours of a weatherbeaten mosque wall in a Nakuru maize town — the *wall
itself*: sun-faded plaster, gently peeling paint, a soft dust patina. Subtle and quiet; the Sakina
geometry is at most a faint ghost in the surface, if there at all.

## Subject (Layer C)

A weathered, sun-faded **plaster wall** — patchy faded whitewash over rough lime render, **gently peeling
paint**, soft dust patina, fine hairline cracks, a faint water-stain. **Subtle**: a quiet, even,
almost-plain surface that recedes — low relief, soft daylight, nothing dramatic. The Sakina geometry, if
present at all, is a **faint ghost** barely readable in the plaster, never a foregrounded pattern. **No
literal mosque, building, window, or door** — only the wall's surface and its colours.

## Palette (this artwork)

The Sakina palette pulled toward weathered-Nakuru ([research.md](../../research.md)): grounds
**sun-bleached cream `#ECE4D4` + warm dust `#D9C8A4`** (~75%); sparse accents **faded mosque-green
`#8E9C85`, desaturated murram red-earth `#A56A4E`, dust-grey `#ABA294`, a touch of faded maize-gold
`#C8A865`**. Desaturated, light-to-mid, low contrast. For this subtle piece the wall's cream/dust dominates even more —
the faded green and murram appear only as quiet stains in the plaster, not motifs.

## The prompt

Climbs the [ladder](../../prompt-ladder.md) on the Sakina binding. The locked `--sref` is pastel, so
**`--sw` is lowered** here to let the weathered earthy palette and texture come through. Starting point
(tune in the session):

```
a weathered sun-faded plaster wall, gently peeling paint, patchy faded whitewash over rough lime render, soft dust patina, fine hairline cracks, subtle low-relief texture, faded earthy palette — sun-bleached cream and warm dust, faint stains of faded mosque-green and desaturated red-earth murram, very low saturation, low contrast, soft diffuse daylight, matte, even all-over surface, quiet and almost plain, still, a faint ghost of geometric pattern barely worn into the plaster --sref 5152366415 --sw 40 --style raw --s 50 --c 0 --ar <device> --no vivid, saturated, neon, jewel tones, glossy, sheen, wet, new clean plaster, polished, dramatic cracks, ruin, rubble, graffiti, mosque, dome, minaret, building, arch, window, door, figures, people, faces, flowers, plants, objects, text, calligraphy, high contrast, busy, ornate, bold pattern
```

**The subtlety dial is `--sw`** — it sets how present the geometry is. At ~60 the star pattern still reads
clearly; **drop toward 30** for subtler / more-wall, raise for more pattern. (Drop `--sref` entirely for a
plain weathered wall with no geometry at all.)

## To record once made

- [ ] Final `--sw`, `--seed`, mode/stylize kept, any wording changed.
- [ ] Exports per device (Layer D — [ladder](../../prompt-ladder.md) table):
  - [ ] Galaxy S24 — 1080×2340 · iPad 9 — 2160×1620 · MacBook Pro 14 M4 — 3024×1964
- [ ] Cleared the [curation](../../curation.md) bar (it recedes; mostly empty; quiet, not clever).
- [ ] Named the wallpaper (working title retired).

## Not this

No depicted mosque, building, window, door, arch, dome, or minaret — the wall's *surface* only. Not a
vivid or freshly-painted wall (it's sun-faded and weathered). Not a dramatic, crack-everywhere ruin or
graffiti — weathering is a quiet patina, not damage. Not a bold foregrounded pattern — geometry stays a
faint ghost, if there at all.

---

## Constitution Check

1. **Serves:** I (one finite, glanceable thing; it recedes), VI (sun-faded, low saturation, low contrast,
   no alarm), the [Sakina](./STYLE.md) style, and the *energy-not-depiction* reading — the wall's feeling,
   not the building.
2. **Violates:** the suite monochrome rule — by Sakina's recorded calm-colour departure (research-earned,
   §charter). Otherwise none — abstract, no mosque/figures/text; confirmed vs Articles + banned patterns +
   the [curation](../../curation.md) bar.
3. **Subtracts:** the "Not this" list trims the over-reaches (a depicted mosque, a vivid or ruined wall)
   before a single generation.
4. **Calm:** if no keeper comes, the artwork stays draft and the set keeps; failure is "discard and stop,"
   never alarm.
