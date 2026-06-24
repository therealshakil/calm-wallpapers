# The prompt ladder (method)

How to climb from a blank prompt to a finished, device-fit wallpaper — by hand. This is shared *method*:
every style and every artwork uses it. The look and parameters are in the [recipe](./recipe.md); this is
the *process*. Backed by [research.md](./research.md).

The ladder has four layers, stacked into one prompt and climbed in order. The fixed calm constraints sit
at the bottom; the **style** and its **theme** arrive on the upper rungs (so the look is calm *before* it
is themed); the **device** target comes last. You don't open with the theme — you climb to it.

## Layer A — the calm base (universal; every prompt inherits it)
From [research.md](./research.md). Invariant across all calm styles:
- Mid-low visual complexity; few marks; **~70–85% empty**. Soft fascination — never busy, never sterile.
- One subject, **small (~10–25% of frame), placed low and off-centre**; top and centre kept clear for
  clocks, widgets, icons.
- **Low contrast** — soft grey ink, no jet-black on pure white. (In monochrome, contrast is the main
  arousal dial.)
- Soft broad curves over fine sharp hatching; loose hand-drawn imperfection (wabi-sabi); varied light
  line weight.
- Biophilic / slow / undemanding subjects. **No faces, no direct gaze, no motion energy.**

## Layer B — the style + its theme (per [style](./specs/))
The art direction and subject vocabulary, defined by the style's `STYLE.md`. First style:
[ink on paper, Peanuts](./specs/ink-peanuts/STYLE.md). *This is the rung where the theme arrives.*

### How a style maps to Midjourney
Our "style" is an art direction — bigger than any single Midjourney flag, but it *binds* to a few. The
split that matters is per-style vs universal:

| Our concept | Midjourney mechanism | Scope |
|---|---|---|
| A style's **look** (the family resemblance) | `--sref <code>` (+ `--sw` weight, `--sv` version), anchored to one committed image | per style |
| A style's **register & motifs** | the prompt fragment — the words | per style |
| The **calm base** (shared by every style) | `--style raw`, low `--s`, `--c 0`, the `--no` list | universal — here + the [recipe](./recipe.md), never per-style |
| **Reproducibility** vs MJ drift | the committed anchor image + the recorded `--v` | per style |

So **one style = one anchor image + its `--sref` code (+ sw/sv/version) + a prompt fragment + a motif
vocabulary**, recorded in the style's `STYLE.md` (its "Midjourney binding"). Different styles = different
anchors and codes. To *generate from a style*, load its binding onto this ladder, then add the subject
(Layer C) and the device `--ar` (Layer D).

**Durability note (Article IX):** MJ `--sref` codes are tied to model versions and can drift when MJ
updates. The **committed anchor image is the source of truth**; the code is a convenience pointer. If a
code stops rendering right, re-derive it from the anchor (`--sref <anchor image URL>`, or `--sref random`
→ pick → lock the new code). Flag values here are as of MJ v6/v7 — confirm against current Midjourney
docs before locking a style.

## Layer C — the subject (per [artwork](./specs/))
One quiet subject from the style's vocabulary — one artwork, one thing. Lives in the artwork's spec.

## Layer D — the device target (last; universal mechanics)
Aspect ratio, composition safe-areas, resolution, and the per-device paper/ink tweak. Make the calm,
on-theme image first; fan out to devices last. Export at native pixels (already retina/physical — no
extra @2x). Tag the colour profile so the OS colour-manages instead of guessing. Tweaks are directional,
confirmed by eye on each panel.

| Device | Export | `--ar` | Paper / ink tweak | Colour tag |
|---|---|---|---|---|
| Galaxy S24 (OLED) | 1080×2340 | `6:13` (≈19.5:9 ↕) | Warmer paper, a touch dimmer; ink can go **deepest** (true-0 black). Keep upper ~10% + lock-clock zone quiet; centre-safe (Android crops + pans edges). View in Natural mode. | P3 or sRGB |
| iPad 9 (sRGB LCD) | 2160×1620 | `4:3` | **Warmest** paper (counters blue-ish white); **lightest** ink (milky black floor — lift it so it reads as deliberate dark-grey, not failed black). Stay inside sRGB. | sRGB |
| MacBook Pro 14 M4 (mini-LED) | 3024×1964 | `3:2` (crop to native) | Near-master warmth; the real lever is **lower display brightness** so paper doesn't glow. Ink can go deep. Keep menu-bar + Dock zones calm. View in a reference mode. | P3 or sRGB |

Per-device tuning is justified by how it *reads*, never by an eye-health claim (the blue-light health
framing is not evidence-based — see [research.md](./research.md)).

On the MacBook, the light + dark pair can optionally be packaged as one macOS dynamic wallpaper that
follows the system appearance — see [dynamic-wallpaper.md](./dynamic-wallpaper.md).

## The ladder, in prompts
1. **Base + composition** — establish the Layer A calm base and the emptiness on the target ratio with a
   neutral placeholder subject. Discover/lock the style's `--sref` (see [recipe](./recipe.md)).
2. **Style + theme in** — bring in the style's register and swap to a theme subject. *The theme arrives
   here.*
3. **Refine** — tune line weight, contrast, subject scale and placement. A few iterations, then stop.
4. **Device fan-out** — re-render at each device's aspect ratio and export with its paper/ink tweak.

## The calm making-ritual
A finite session. Generate a few, pick what's right, **stop** — no reroll treadmill (identity.md). An
off-brand, busy, or filtered generation is discarded, not chased. If a rung won't behave, drop back one
or close the tab; the picture will keep.

---

## Constitution Check

1. **Serves:** I (a finite ritual with an end), VI (calm built into Layer A before anything else), IX
   (hand-run, no fragile dependency), and the suite identity (one calm hand across the set).
2. **Violates:** none — confirmed vs Articles + banned patterns. "No reroll treadmill" is from
   identity.md; per-device tuning is held to a calm size and justified by appearance, not a health promise.
3. **Subtracts:** removes prompt drift (constraints inherited, not re-remembered) and the open-ended
   iteration trap; declines automation, per-panel ICC profiles, and batch generation.
4. **Calm:** the empty session is a first-class path; failure is "discard and stop," never alarm; no
   motion to honour `prefers-reduced-motion` against.
