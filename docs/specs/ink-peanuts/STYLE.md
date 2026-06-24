# Style — ink on paper, Peanuts

**Status:** draft · **Date:** 2026-06-24 · **The first calm style.**

The art direction every artwork in this folder shares. A style is **Layer B** of the
[prompt ladder](../../prompt-ladder.md): the register and subject vocabulary that arrive on the upper
rungs, once the universal calm base (Layer A) is set. Other calm styles may follow; this is the first.

## The register

**Peanuts + poetry**, straight from the suite [identity](https://github.com/shakilclark/calm/blob/main/docs/identity.md):
warm, plain, hand-made, a little wistful — big heart, few marks. Meaning from few marks and a lot of
quiet. Gentle and undemanding; **warmth over wit**, never urbane. Confident black ink on warm off-white
paper (light) / bone-white ink on soft off-black (dark), single-ink line work only — no gradients, no
shading, no 3D, no gloss.

## Subject vocabulary

Quiet, slow, biophilic things that ask nothing. A starting list — it firms up as artworks land:

- a bare branch · a single leaf · grasses bending
- a crescent moon · a hill ridge under a wide sky · drifting cloud
- still water, one ripple · fog
- a kite high in a huge sky · a closed book · a single mug · a folded letter
- a small animal asleep, or a lone figure seen **from behind** (never a face, never a direct gaze)

Avoid anything that echoes a known character or trademark — describe the quiet *quality*, not the IP.

## The style's prompt fragment

Drop this onto the Layer A base (see [recipe](../../recipe.md) for full parameters):

```
... loose hand-drawn pen-and-ink, warm and a little wistful, plain and gentle, big feeling from few
confident marks, single-ink line work, no shading no gradient ...
```

- **Locked `--sref`:** _to set_ — once a first artwork's anchor is chosen, record its `--sref` code here
  so every artwork in this style reads as one hand. (See [recipe](../../recipe.md), "keeping a set
  consistent".)

## Artworks in this style

| # | Artwork | Status |
|---|---|---|
| 001 | [Crescent moon](./001-crescent-moon.md) | draft |

---

## Constitution Check

1. **Serves:** the suite identity (Peanuts ink + poetry, monochrome), VI (warmth over alarm; soft, low
   register), I (a bounded vocabulary, not an open feed of subjects).
2. **Violates:** none — single-ink, monochrome, no faces/gaze (Layer A holds the calm); confirmed vs
   Articles + banned patterns.
3. **Subtracts:** one register and a finite subject list keep the set coherent and small — fewer
   decisions per artwork, not more.
4. **Calm:** the vocabulary is all slow, undemanding things; the register is gentle by definition; happy
   and quiet paths inherit from the [ladder](../../prompt-ladder.md).
