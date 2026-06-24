# Research log — calm-wallpapers

Short entries backing the calls in the specs. Each: the question, what the evidence said, the call it
drove, and sources (graded). Honest where something is reasoned-not-sourced. Method follows the suite's
[research-method.md](https://github.com/shakilclark/calm/blob/main/docs/research-method.md).

Grades: **A** = peer-reviewed / standards body or manufacturer spec · **B** = reputable lab / review /
practitioner consensus · **C** = blog / forum / secondary.

---

## What makes a still monochrome image calm? (2026-06-24)

**Q:** The look is fixed (monochrome ink on paper). What art-direction makes a *still* image genuinely
low-arousal and restful, not just pretty?

**Found:**
- **Low visual complexity restores; high complexity taxes.** Ulrich's stress-recovery work and Kaplan's
  Attention Restoration Theory ("soft fascination" — gentle, effortless interest, not attention-grabbing).
  Stressed people prefer *lower* complexity — and a wallpaper is seen on hard days. **(A)**
- **Mid-range fractal structure is the preference peak** (Spehar/Taylor: box-counting D ≈ 1.3–1.5, across
  nature, maths, and Pollock; preference falls for both sparse-sterile and busy-dense). Taylor reports
  large stress reduction from mid-D patterns (his figure ~60% — his claim, exact protocol not verified
  here). **(A** for the preference peak; **B** for the stress figure.**)**
- **In monochrome, contrast is the main arousal dial** — all signal rides the luminance channel, which is
  the one that amplifies emotional/arousing content. Low contrast reads calmer and stays legible for
  broad soft forms; fine sharp detail fights low contrast and adds fatiguing high-frequency energy
  (departures from the natural ~1/f spectrum read as unpleasant). **(A)**
- **Curved/soft forms read safe; sharp/angular forms raise arousal** (curvature preference is
  cross-cultural; angular contours engage threat processing). **(B+)**
- **Direct gaze / faces looking at the viewer capture and hold attention and raise arousal** — the
  opposite of peripheral calm. Averted or no gaze. **(A)**
- **Calm technology (Weiser & Brown):** the governing principle — "informs but doesn't demand attention;
  sits in the periphery." A wallpaper *is* peripheral tech. Plus *ma* (intentional void) and *wabi-sabi*
  (calm in hand-made imperfection). **(A** for calm-tech; **B/C** for the cultural aesthetics.**)**
- *Reasoned, not sourced:* the fractal findings are from dense stimuli, not sparse line art — but the
  lever (mid-range, organic, statistically-self-similar marks) is achievable with a few gently irregular
  lines. Off-centre-beats-centre for recession is synthesis, not a measured result.

**Call (→ [prompt-ladder.md](./prompt-ladder.md), Layer A — the calm base):** every prompt inherits a fixed base — mid-low complexity,
small subject (~10–25% of frame) low and off-centre, ~70–85% empty, low contrast (no jet-black on pure
white), soft broad curves over fine sharp hatching, hand-drawn imperfection, biophilic/slow subjects, and
**no faces, no direct gaze, no motion energy**.

**Sources:** Ulrich et al. 1991 (J. Env. Psych.); Kaplan ART (Basu, Duvall & Kaplan 2019, SAGE); Spehar
et al. 2003 "Universal aesthetic of fractals" (*Computers & Graphics*); luminance-channel amplification
(PMC4361366, PMC3818477); contrast × spatial frequency (JOSA A 13-10-1953); 1/f preference (PMC7308450);
curvature/threat (Silvia & Barona; PMC4603793); direct-gaze arousal (PMC4072644, PMC6558178); Weiser &
Brown "Designing Calm Technology" (MIT).

---

## Is per-device "paper/ink" tuning calm, or over-engineering? (2026-06-24)

**Q:** Should a monochrome wallpaper be tuned per device (Galaxy S24, iPad 9, MacBook Pro 14 M4)? Devices
differ; "personalised colour profile per device" was floated as itself calm.

**Found:**
- **The same hex renders differently per panel.** S24 (OLED, P3, true-0 black, runs to ~1400+ nits, cool
  Vivid default) shows ink deepest and contrast highest. iPad 9 (sRGB LCD, non-laminated, elevated
  ~0.5 cd/m² black floor, slightly blue whites, 500 nits) shows milky blacks and a cool-ish paper. MacBook
  Pro 14 M4 (mini-LED, P3, 1000 nits SDR, reference modes) is accurate but the off-white can *glow* at
  full brightness. **(A** specs; **B** rendering behaviour.**)**
- **The honest calm justification is appearance, not eye-health.** "Warm paper = healthier eyes / less
  strain via less blue light" is **not** evidence-based — the AAO does not recommend blue-light blocking,
  and a 2023 Cochrane review (17 RCTs) found blue-light filtering makes ~no difference to strain or sleep.
  Digital eye strain is caused by *use* (reduced blinking, dryness), not screen blue light. **(A)**
- **What *is* supported is comfort/preference:** warmer, lower-brightness whites tend to read as more
  restful (lighting-ergonomics studies — directional, not display-specific). True Tone, Night Shift, and
  Samsung Eye Comfort Shield are real, shipping, opt-in — but they *move the white point themselves*, so
  tuning paper colour with them on is aiming at a moving target. **(A** features; **B** comfort.**)**

**Call (→ [prompt-ladder.md](./prompt-ladder.md), Layer D — device target):** per-device tuning is worth a *calm-sized* amount — one
master + three small tweaks + correct colour tagging + a brightness note. Justify by how it *reads*, never
by an eye-health promise. Going further (per-panel ICC profiles, gamma curves) is the over-engineering
trap and would make a wallpaper a timesink — declined. Per-device targets table lives in the spec.

**Sources:** Apple spec sheets (iPad 9 — support 111898; MacBook Pro 14 M4 — 121552; reference modes —
108321) **(A)**; GSMArena S24 lab **(B)**; NotebookCheck iPad 9 review **(B)**; TechSpot XDR review **(B)**;
AAO blue-light guidance + Cochrane 2023 blue-light-lens review **(A)**; MDPI Sustainability CCT/comfort
**(B)**; Samsung Eye Comfort Shield support **(A)**.
