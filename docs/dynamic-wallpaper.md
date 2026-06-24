# macOS dynamic wallpaper (method)

How to package an artwork's **light + dark pair** into one macOS `.heic` that follows the system
appearance — by hand. Optional, MacBook only. Backed by [research.md](./research.md).

## The calm decision: appearance pair only

macOS supports three dynamic modes — appearance (light/dark), solar, and time-of-day. We use **only the
appearance pair**:

- It's two images — the exact light + dark pair the [style](./specs/) already produces.
- It follows the manual Light/Dark toggle and then **stops**. One meaningful, glanceable state change —
  not an always-shifting desktop.
- The solar/time "day-arc" is **declined**: ~16 hand-tuned frames, only animates on Auto, has documented
  Sequoia bugs, and a perpetually-moving wallpaper is the attention-pull a calm tool resists (Article I,
  VI).

A build-time tool here (below) is a hand tool, not a shipped dependency — nothing fragile reaches the
artifact, which is plain image data. Same logic as [the-midjourney-exception](./the-midjourney-exception.md).

## The fixed constant

For light = image 0 and dark = image 1, the appearance plist is always `{ l = 0; d = 1; }`. Its
Base64 (reusable verbatim, no per-artwork authoring) is:

```
YnBsaXN0MDDSAQIDBFFsUWQQABABCA0PERMAAAAAAAABAQAAAAAAAAAFAAAAAAAAAAAAAAAAAAAAFQ==
```

## Route A — wallpapper (fewest steps)

One small tool, one JSON, one command. (`wallpapper` is MIT but last released 2023 — fine as a hand
tool; see the calm note above.)

1. `brew tap mczachurski/wallpapper`
2. `brew install wallpapper`
3. With `light.png` and `dark.png` in a folder, a `wallpaper.json`:
   ```json
   [
     { "fileName": "light.png", "isPrimary": true, "isForLight": true },
     { "fileName": "dark.png", "isForDark": true }
   ]
   ```
4. `wallpapper -i /abs/path/wallpaper.json -o /abs/path/artwork.heic`

## Route B — libheif + exiftool (lowest dependency)

Well-maintained, reputable tools; you attach the fixed constant yourself.

1. `brew install libheif exiftool`
2. `heif-enc -L /abs/path/light.png /abs/path/dark.png -o /abs/path/artwork.heic` (`-L` = lossless;
   light first so it's index 0)
3. Attach the `apple_desktop` XMP (namespace `http://ns.apple.com/namespace/1.0/`, property `apr`)
   carrying the Base64 constant above. *Verify the exact exiftool/exiv2 incantation on first run —
   writing a custom XMP namespace needs a small config; confirm the metadata reads back before trusting
   it.*

Then: System Settings → Wallpaper → Add Photo → pick the `.heic`. Set Appearance to Light or Dark to
check each still; Auto follows the system.

## Caveats

- **Lossless, or the ink suffers.** HEIC is lossy and block-based — fine high-contrast linework can ring.
  Encode lossless, author at native **3024×1964** (MacBook Pro 14 M4), inspect at 100%. There's no
  PNG-quality dynamic container; HEIC is the only one macOS reads.
- **One resolution is enough** — macOS scales a single image per frame.
- **No signing or permissions** — a `.heic` is plain data. If the picker caches an old version, re-add or
  rename the file.

---

## Constitution Check

1. **Serves:** VI (the one calm state change — match appearance, then stop; no perpetual motion), I (a
   finite artifact, glanceable), IX (hand-run build tool; nothing fragile ships).
2. **Violates:** none — the solar/time arc (the part that would breach "no autoplaying/looping motion")
   is explicitly declined; confirmed vs Articles + banned patterns.
3. **Subtracts:** declines two of three modes and all per-artwork plist authoring (one fixed constant);
   optional and MacBook-only, so it adds nothing for the other devices.
4. **Calm:** honest about the HEIC linework risk and the unverified metadata step; the day-arc is refused
   on calm grounds, not just effort.
