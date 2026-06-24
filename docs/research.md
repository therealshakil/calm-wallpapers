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

---

## Should calm-wallpapers ship macOS dynamic wallpapers? (2026-06-24)

**Q:** A macOS dynamic wallpaper can shift with the system. We already make a light + dark pair per
artwork — is packaging that as a dynamic `.heic` calm, and how?

**Found:**
- A macOS dynamic wallpaper is **one `.heic`** holding the images plus an `apple_desktop` XMP key whose
  value is a Base64 binary plist. Three modes: **appearance** (light/dark pair — `ap` dict `{l,d}`),
  **solar** (`si` — ~16 frames with sun altitude/azimuth), **time** (`ti` — frames by time of day). **(A**
  — Ole Begemann reverse-engineering gist, NSHipster, Harshil Shah Catalina write-up.**)**
- **The appearance pair is a fixed constant.** For light=index 0 / dark=index 1 the plist is always
  `{ l = 0; d = 1; }`; the Base64 is reusable verbatim — no plist authoring per artwork. (Decoded and
  verified.) Needs **exactly two images**. **(A)**
- The appearance pair **follows the manual Light/Dark toggle**, not just Auto — set Dark, get the dark
  still, then it stops. One meaningful, glanceable state change. **(A)**
- Solar/time need ~16 frames, only animate on **Auto**, and have **documented Sequoia bugs** (solar
  stalls once Dark is on). **(A** mechanism; **C** the bug — forum-sourced.**)**
- **HEIC is lossy + block-based** — the worst case for high-contrast thin ink lines (ringing/mosquito
  artefacts). Mitigate: encode **lossless** (`heif-enc -L`), author at native resolution, inspect at
  100%. There is no PNG-quality dynamic-wallpaper container; HEIC is the only format macOS reads. **(B)**

**Call (→ [dynamic-wallpaper.md](./dynamic-wallpaper.md)):** ship the **appearance (light/dark) pair
only**. Skip the solar/time day-arc — it's over-engineering (16 hand-tuned frames, Auto-only, buggy) and
an always-shifting desktop is the attention-pull a calm tool resists. The pair gives the one calm state
change (match the appearance, then stop) from two images and a constant. Build-time tools (`wallpapper`,
or `libheif`+`exiftool`) are hand tools, not shipped dependencies — same logic as
[the-midjourney-exception](./the-midjourney-exception.md) — so a tool's staleness is acceptable here.

**Sources:** Ole Begemann gist (format) **(A)**; NSHipster *macOS Dynamic Desktop* **(A)**; Harshil Shah
*Dynamic Wallpapers in Catalina* **(A)**; `wallpapper` (GitHub, MIT, last release 2023) **(B)**; Equinox
(open-source GUI) **(B)**; Apple Support — light/dark appearance **(A)**; Apple Dev Forums #764238
(Sequoia solar bug) **(C)**.

---

## What is Islamic calm? (2026-06-24)

**Q:** What is Islamic calm — the *energy, not the depiction* ("the spirit of Islam") — as the basis for a
future style? Official / scholarly, to read before committing.

**Found:**
- **Spiritual vocabulary.** *sakīna* — peace that descends and settles on the heart (Qur'an 48:4);
  *ṭumaʾnīna* — the heart at rest, reached through *dhikr* / remembrance (13:28, "in the remembrance of
  God hearts find rest"); the root *s-l-m* gives both *salām* (peace) and *Islām* (surrender). Calm is
  **received/entrusted, not strained**. **(A** Qur'an.com; **B** tafsir.**)**
- **Non-figuration & its rationale.** Aniconism holds firmly for *sacred* art — never a blanket ban
  (courtly art is full of figures); it turns from depicting *things* toward the unrepresentable —
  *tawḥīd* (divine oneness). "Energy not depiction" is the sacred register of the tradition. **(A** Met
  essays; **B** Wikipedia.**)**
- **The calm mechanism = no focal point.** The pattern continues past the frame; weight is even
  everywhere; the eye never locks — it drifts and rests at once. Plus deep symmetry with subtle variation
  (unity in multiplicity), flowing arabesque line (breath/growth, the living counterpart to fixed
  geometry), generous void, and soft light (*nūr*) over hard contrast. **(A** Met geometric/vegetal;
  Critchlow.**)**
- **Honest interpretation caveat.** The Qur'anic vocabulary is canonical, but the claim that pattern
  *deliberately encodes* this theology is the **perennialist reading** (Burckhardt, Nasr) — widely held
  but interpretive; **Grabar** (*The Mediation of Ornament*) is the cautious art-historical counter-voice.
  Hold the symbolism as interpretation, not documented intent. **(A)**
- **Craft caveat (confirmed).** Midjourney cannot render Arabic (its docs: text works best in Latin) → AI
  "calligraphy" of scripture is gibberish and disrespectful. Geometry and arabesque carry no text and are
  safe. **(A** MJ docs.**)**

**Call (→ the `sakina` style; not yet locked):** capture the *energy, not the depiction* —
endless, **low-density** geometry (*girih*) and/or arabesque (*islīmī*), **no focal point**, generous
void, soft luminous low contrast (*nūr*); monochrome (palette decided at commit). Hard exclusions: **no
AI Arabic / calligraphy, no figures, no literal mosque scenes.** For wallpaper: large-scale, low-density,
dissolving into void (leaves room for icons); describe the *geometry + energy directly*, not the word
"Islamic" (which pulls Midjourney toward clichés + pseudo-script).

**Sources:** Qur'an.com 48:4 & 13:28 **(A)**; Met essays — Figural Representation, Geometric Patterns,
Vegetal Patterns **(A)**; Burckhardt *Art of Islam: Language and Meaning* **(A)**; Nasr *Islamic Art and
Spirituality* **(A)**; Critchlow *Islamic Patterns* **(A)**; Grabar *The Mediation of Ornament* **(A**,
counter-voice**)**; Aniconism in Islam — Wikipedia **(B)**; Midjourney text-generation docs **(A)**.

---

## Calm Islamic colour — Alhambra + Swahili coast (2026-06-24)

**Q:** The `sakina` style opens to gentle colour ("doesn't have to be monochrome, still has to be
calm"). Anchors: the **Alhambra** and **East Africa / the Swahili coast**. What's the *calm* — muted,
low-arousal — end of these palettes?

**Found:**
- **Saturation is the main calm lever, not hue.** Desaturated = low-arousal; saturated = high-arousal. A
  nuance that matters: in the low-saturation range hue differences nearly vanish and **brightness**
  dominates — *dark* muted tones can be as arousing as vivid red, while **light + low-saturation** reads
  most restful. So calm = low saturation + light-to-mid value + low contrast + a neutral ground that
  dominates. **(A** PMC saturation/arousal; **B** colour-emotion reviews.**)**
- **Alhambra now reads as warm honey stone + aged cream plaster** — originally polychrome (lapis/azurite
  blue, malachite green, cinnabar red, gold), most faded. The calm parts: the lime-white, honey ochre,
  dusty terracotta. Too vivid as-is: saturated lapis blue, malachite green, cinnabar, and especially
  **gold** (the top cliché to avoid). **(A** Alhambra pigment study, Patronato; **B** Dosde.**)**
- **Swahili coast is naturally calm and earthy** — coral-rag stone, lime-washed cream/white, warm sand,
  muted ochre, weathered grey, aged-teak browns, soft Indian-Ocean teal. The *textiles* (kanga/kitenge)
  are the vivid part — keep them out. **Indigo** (a coastal trade craft) desaturates into a dusty blue
  that bridges both worlds. **(A** UNESCO Stone Town; **B** ArchDaily, African History Extra.**)**
- Colour meaning, lightly: **green** = Paradise / the middle way (Qur'an 18:31, 55:76 — solid);
  blue/turquoise as protective (cultural, don't overclaim). **(B)**

**Call (→ `sakina` STYLE.md palette):** a small, desaturated, light palette — neutral ground
dominant (~85%), sparse muted accents. Ground **Lime-Wash `#EDE6D6`** + **Warm Sand `#DAC9A6`**; accents
**Dusty Indigo `#5E7287`**, **Muted Sage `#8A9A82`**, sparse **Soft Terracotta `#B07A5E`** (Indian-Ocean
**Muted Teal `#6E9C99`** an optional swap); hairline **Faded Ink `#4A4A45`** for line only. One accent
leads per piece. No gold, no gloss, no pure-black/dark-heavy field. Hex values are calibrated
approximations, not measured. **This is a deliberate departure from the suite's locked monochrome
identity — a chosen exception for this style, recorded as such, not drift.**

**Sources:** PMC *Saturation & anger (low-saturation range)* **(A)**; Psychonomic Society colour-emotion
**(B)**; Alhambra pigment study (ResearchGate) **(A)**; Patronato de la Alhambra — Mexuar tiles **(A)**;
Dosde *Tilework in the Alhambra* **(B)**; UNESCO Stone Town of Zanzibar **(A)**; ArchDaily *Swahili
architecture* / *Colour in Islamic architecture* **(B)**; *Green in Islam* (Qur'an refs) **(B)**.

---

## Calm Islamic texture — Alhambra + Swahili coast (2026-06-24)

**Q:** What surface textures carry Islamic calm (Alhambra + Swahili), kept matte/restful and recessive
for a wallpaper?

**Found:**
- **Pick the matte side of each tradition.** Alhambra has a deliberate hierarchy: glossy saturated
  **zellij** below the dado, **matte carved plaster** (*yesería*, low-to-deep relief, soft self-shadow)
  above. The upper-wall plaster is the calm reference; the glazed tile and gilded **muqarnas** are the
  busy end. **(A/B** stucco + zellij sources.**)**
- **Swahili = weathered lime over coral.** Coral-rag stone + lime/sand mortar, **lime-washed** chalky
  cream — soft, porous, sun-bleached, hand-laid. The carved **Zanzibar/Lamu doors** are gorgeous but a
  *busy* texture — evoke at most as faint grain, never a literal subject. **(A/B** Swahili architecture;
  museum mkeka object.**)**
- **Calm texture traits:** matte over glossy, shallow over deep relief, weathered over crisp, diffuse
  light over dramatic, **even all-over over focal**, low-contrast tonal range. Suggest texture *subtly* —
  soft plaster grain, gentle low relief, paper-like tooth — felt before noticed. Tadelakt (Moroccan, not
  Swahili) is a useful near-matte *reference* only. **(A/B** + calm-wallpaper practice **C**.**)**

**Call (→ `sakina` STYLE.md texture):** evoke 3–4 quiet textures — **matte carved plaster (low
relief)**, **limewashed coral wall**, **soft hand-pressed/near-matte plaster**, optional **fine woven
palm tooth** — as a *ground*, never a subject. Hold to matte, shallow relief, diffuse soft light, even
all-over, low contrast. Avoid glaze/sheen, gilded muqarnas, deep-carved doors.

**Sources:** *Stucco decoration in Islamic architecture* — Wikipedia **(A/B)**; *Zellij* — Wikipedia
**(A/B)**; *Swahili architecture* — Wikipedia **(A/B)**; Mkeka mat — Ethnological Museum Berlin **(A)**;
ArchDaily *Swahili architecture* **(B)**; *Tadelakt* — Wikipedia / Remodelista **(A/B)**.
