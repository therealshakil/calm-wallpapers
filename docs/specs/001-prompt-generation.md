# Spec 001 — Prompt generation

**Status:** draft · **Date:** 2026-06-24 · **App:** calm-wallpapers

A repeatable, hand-run process for writing Midjourney prompts that produce calm, on-theme, device-fit
wallpapers — without turning the making into a treadmill.

## Why

The [recipe](../recipe.md) covers the look and the parameters. What's missing is a *process*: how to go
from a blank prompt to a finished set that is (a) genuinely calm — research-backed, not vibes — (b) on a
chosen editorial theme, and (c) right on each device I actually use. Without a process, every session
re-invents the prompt and the set drifts. With one, the calm constraints are inherited, not remembered.

Serves Article I (a finite, glanceable thing made by a finite ritual), VI (low-arousal by construction),
and the suite identity (one calm hand across the set).

## What it does

A **prompt ladder** — four layers, stacked into one prompt, climbed in order. The fixed constraints sit
at the bottom; the theme arrives on the upper rungs (so the look is calm *before* it is themed); the
device target comes last. You don't open with the theme — you climb to it.

### Layer A — the calm base (fixed, every prompt inherits it)
From [research.md](../research.md) — the art-direction findings. Invariant:
- Mid-low visual complexity; few marks; **~70–85% empty**. Soft fascination, never busy, never sterile.
- One subject, **small (~10–25% of frame), placed low and off-centre**; top and centre kept clear for
  clocks, widgets, icons.
- **Low contrast** — soft grey ink, no jet-black on pure white. (In monochrome, contrast is the main
  arousal dial.)
- Soft broad curves over fine sharp hatching; loose hand-drawn imperfection (wabi-sabi), varied light
  line weight.
- Biophilic / slow / undemanding subjects. **No faces, no direct gaze, no motion energy.**

### Layer B — the theme (variable; reached on the later rungs)
The editorial register and subject vocabulary. **First theme: Peanuts + poetry** — warm, plain,
hand-made, a little wistful; meaning from few words; big heart, few marks. Subject vocabulary stays
quiet: a bare branch, a crescent moon, a single mug, a closed book, a small dog asleep, a kite in a
huge sky, a lone figure seen from behind. Warmth over wit, always (Peanuts-gentle, never New-Yorker-wry).

### Layer C — the subject (one per wallpaper)
Pick **one** subject from the theme vocabulary. One wallpaper, one quiet thing.

### Layer D — the device target (last)
Aspect ratio, composition safe-areas, resolution, and the per-device paper/ink tweak (table below). The
calm, on-theme image is made first; the device fan-out is the final rung.

### The ladder, in prompts (this is the "later prompts" path)
1. **Base + composition** — establish the calm base and the emptiness on the target ratio with a neutral
   placeholder subject. Discover/lock a style with `--sref` (see [recipe](../recipe.md)).
2. **Theme in** — bring in the Peanuts-poetry register and swap to a theme subject. *This is where the
   theme arrives.*
3. **Refine** — tune line weight, contrast, subject scale and placement. A few iterations, then stop.
4. **Device fan-out** — re-render at each device's aspect ratio and export with its paper/ink tweak.

### Per-device targets (Layer D)
Export at native pixels (already retina/physical — no extra @2x). Tag the colour profile so the OS
colour-manages instead of guessing. Tweaks are directional, confirmed by eye on each panel.

| Device | Export | Aspect | Paper / ink tweak | Colour tag |
|---|---|---|---|---|
| Galaxy S24 (OLED) | 1080×2340 | 19.5:9 ↕ | Warmer paper, a touch dimmer; ink can go **deepest** (true-0 black). Keep upper ~10% + lock-clock zone quiet; centre-safe (Android crops + pans edges). View in Natural mode. | P3 or sRGB |
| iPad 9 (sRGB LCD) | 2160×1620 | 4:3 | **Warmest** paper (counters blue-ish white); **lightest** ink (milky black floor — lift it so it reads as deliberate dark-grey, not failed black). Stay inside sRGB. | sRGB |
| MacBook Pro 14 M4 (mini-LED) | 3024×1964 | ~1.54:1 | Near-master warmth; the real lever is **lower display brightness** so paper doesn't glow. Ink can go deep. Keep menu-bar + Dock zones calm. View in a reference mode. | P3 or sRGB |

### Happy path
A short session climbs the ladder and yields a few calm, on-theme wallpapers, exported per device,
reading as one hand's work.

### Quiet & empty path
A session that produces nothing keepable is fine. The set keeps; you stop. An empty session is not a
failure — the wallpapers you already have still work.

### When it fails
A generation comes back off-brand, busy, or filtered → discard it, don't chase it. No reroll treadmill
(identity.md). If a whole rung won't behave, drop back a rung or close the tab; the picture will keep.

## Not this (non-goals)

No automation — the ladder is climbed by hand (see [the-midjourney-exception](../the-midjourney-exception.md)).
No per-panel ICC profiles, gamma curves, or calibration hardware (over-engineering — research.md). No
batch generation, no "more like this", no scoring or ranking of outputs. No second theme yet — Peanuts +
poetry first; others wait in [spec-ideas](./spec-ideas.md).

## Research

Both calls are logged in [research.md](../research.md): *What makes a still monochrome image calm?*
(→ Layer A) and *Is per-device "paper/ink" tuning calm, or over-engineering?* (→ Layer D). The per-device
tweaks are justified by appearance, never by an eye-health claim (the blue-light health framing is not
evidence-based — AAO / Cochrane).

## How (the plan)

The process *is* the deliverable — this spec plus the [recipe](../recipe.md). No code. A future helper
that stamps the per-device export sizes would be its own spec and its own Constitution Check, and only
if hand-export proves tedious.

## Open questions

- The Peanuts-poetry subject vocabulary is a starting list — it'll firm up once the first few exist.
- iPad orientation: one 4:3 master that survives rotation, or a portrait and a landscape — decide on
  first contact with the panel.
- Whether one locked `--sref` carries the whole set, or the theme needs its own anchor per subject.

## Tasks

Filled at build time (build = a making session), smallest increments:
- [ ] Climb the ladder once end-to-end for a single subject → one keeper.
- [ ] Lock the set's `--sref` style code in the recipe once an anchor is chosen.
- [ ] Export that keeper for all three devices with the Layer D tweaks; eyeball on each panel.
- [ ] Note any tweak that was wrong on real hardware back into the table.

## Constitution Check

1. **Serves:** I (a finite set made by a finite ritual; the ladder has an end), VI (calm is built into
   Layer A before anything else; low contrast, no motion), IX (hand-run, no fragile dependency; declines
   the calibration-pipeline over-engineering), and the suite identity (one hand across the set).
2. **Violates:** none — confirmed vs Articles + banned patterns. The "no reroll treadmill" rule is lifted
   from identity.md; per-device tuning is held to a calm size and justified by appearance, not a health
   promise.
3. **Subtracts:** removes prompt drift (constraints inherited, not re-remembered) and removes the
   open-ended iteration trap; explicitly declines automation, per-panel ICC profiles, and batch
   generation.
4. **Calm:** the empty session is a first-class path, not an edge case; failure is "discard and stop,"
   never alarm; no motion to honour `prefers-reduced-motion` against; honest that the *making* can turn
   un-calm and names the stop signal.
