# The recipe

How to make a calm wallpaper in Midjourney, by hand. This is a craft doc — you run it, not a script.
It translates the suite's locked [identity](https://github.com/shakilclark/calm/blob/main/docs/identity.md)
into prompts and parameters, and explains the *why* so you can deviate with judgement.

---

## The look we're after

From identity.md, in still form:

- **Monochrome, ink on paper.** Black ink on *warm* off-white (light) or bone-white ink on *soft*
  off-black (dark). Never pure `#000`/`#fff` — a little warmth, so it reads as paper, not screen.
- **Few confident marks.** Hand-drawn pen-and-ink linework. Huge feeling from the fewest lines.
  Gentle, a touch wistful. Never loud, never trying to grab you.
- **Vast empty space.** The subject is small and off to one side. Most of the frame is quiet paper —
  room for your desktop icons, and room for the eye to rest. "Sits in the corner of your eye and asks
  nothing."

**Describe the qualities, never the IP.** Say *gentle hand-drawn ink, simple childlike linework, few
marks, warm and wistful* — not "Peanuts" or "Snoopy". Naming the trademark is both off-limits and
unreliable (it gets filtered). The qualities are what we actually want anyway.

## A prompt, to start from

Light:

```
a single small subject — a sleeping cat curled in the lower-left corner — drawn in gentle hand-drawn
pen and ink, simple confident linework, very few marks, lots of empty warm off-white paper, calm and a
little wistful, minimalist, near-black ink on warm off-white --style raw --s 60 --c 0 --ar 16:10
--no color, colour, gradient, shading, text, watermark, signature, frame, border
```

Dark — same prompt, invert the surface:

```
... bone-white ink on soft off-black paper ...  (everything else unchanged)
```

Swap the subject for whatever is quiet: a crescent moon, a bare branch, a single mug, a folded letter,
a small house under a big sky. Keep it one subject, small, low in the frame.

## The parameters, and why

| Flag | Use | Why it's calm |
|---|---|---|
| `--style raw` | Always | Drops Midjourney's auto-beautify, so the output follows the prompt instead of prettifying it. Restraint over gloss. |
| `--s 50` to `--s 100` | Low stylize | Keeps it prompt-faithful and plain. High stylize invents flourish we don't want. |
| `--c 0` | Low chaos | Low variation between the four tiles — calm, predictable, easier to choose from. |
| `--ar 16:10` etc. | Match the screen | See the table below. |
| `--no color, gradient, shading, text, ...` | Always | Enforces monochrome and a clean field. The negative list does the quiet. |
| `--sref <code>` | Across a set | Locks one visual style across many pictures — see below. The key to a coherent set. |
| `--seed <n>` | When iterating | Reproducible starting point within a session, so a small prompt tweak is comparable. |

Use the current Midjourney version (`--v`); the defaults above hold across recent versions. If a flag
behaves differently in your version, trust your eye over this table.

## Aspect ratios

| Screen | Flag |
|---|---|
| Most desktops / 1080p / 4K | `--ar 16:9` |
| MacBook | `--ar 16:10` |
| Ultrawide | `--ar 21:9` |
| Super-ultrawide | `--ar 32:9` |

Make the wallpaper at the ratio of the screen it's for. A 16:9 image stretched onto an ultrawide stops
being calm.

## Keeping a set consistent

The one thing most likely to break calm across several wallpapers is style drift — they stop looking
like a family. The fix is a **style reference**:

1. Make one piece you're happy with — the anchor.
2. Reuse its style with `--sref <url-or-code>` on every other prompt. (To discover a fresh style, use
   `--sref random`, note the code it gives, then lock that code across the set.)
3. Tune how strongly with `--sw` (style weight) if the reference pulls too hard or too little.

Same `--sref`, same parameters, only the subject changes — and the set reads as one calm hand.

## Resolution

Midjourney's base tiles are around 1024px; its upscale roughly doubles that. Monochrome linework on
empty paper upscales cleanly — there's little detail to smear — so an upscaled tile is usually enough
for a normal display. For a 5K/retina screen you may want a final pass through a dedicated upscaler.
Don't over-engineer this: pick the upscale that looks right and stop.

## The calm making-ritual

This matters as much as the parameters. The making must be calm too, or the repo becomes the thing it
resists.

- **Set an end before you start.** "A handful of subjects, one good version each." A finite session,
  not an open one.
- **No reroll treadmill.** identity.md names this directly. Rerolling for the perfect tile is a
  hyperfocus hole — the slot-machine feeling, dressed as taste. Generate a few, pick what's right,
  stop. A good-enough calm picture beats a perfect one you chased for an hour.
- **Stop when you have enough, not when you've exhausted the ideas.** The set is meant to be small.

If you notice you're rerolling past the point of choosing, that's the signal to close the tab. The
picture will keep.

---

## Constitution Check

1. **Serves:** VI (a low-arousal, monochrome look, specified concretely), I (finite — the ritual builds
   in an end you reach; no reroll treadmill), and the suite's identity §3.
2. **Violates:** none — describes hand-use only; the negative-prompt list and `--c 0` hold the calm.
   Confirmed vs Articles + banned patterns (the "no reroll treadmill" rule is lifted straight from
   identity.md).
3. **Subtracts:** the negative list removes colour, gradient, shading, and text; the ritual removes the
   endless-iteration trap.
4. **Calm:** the doc is honest that the *making* can become un-calm, and names the stop signal rather
   than pretending the tool is calm on its own.
