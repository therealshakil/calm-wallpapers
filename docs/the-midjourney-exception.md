# The Midjourney exception

The suite's [identity](https://github.com/therealshakil/calm/blob/main/docs/identity.md) says, plainly,
**"Not Midjourney."** This repo uses Midjourney. That isn't a contradiction — it's a different use of
the same word, and worth being clear about.

## What identity.md actually objected to

The "not Midjourney" line sits inside §3, under *how a shipped app generates illustration on its own*.
The objection is specific: Midjourney has no durable official API, so an app that generated images from
it would lean on fragile, ToS-risky Discord automation. That fails Article IX — a dependency must be
*essential and responsibly sourced*, something likely to be cared for for years. An automated pipeline
built on an unofficial API is none of those things. The candidates named there (FLUX.1, gpt-image-1,
Imagen) are all things a *machine* can call safely.

## Why hand-use is a different thing

Here, no machine calls anything. A person opens Midjourney, types a prompt, looks, and picks. The
output is a plain image file checked into a repo. Nothing fragile ships; there is no dependency to
break, no key to leak, no automation to drift out of ToS. The tool is a pencil, not a pipeline.

That distinction is the calm one. Article IX is about what a *project depends on to run* — and this
project depends on nothing but the files already in it. The making happened upstream, by hand, and
left no trace to maintain.

## The rule of thumb

> The tool stays in your hands. Nothing automated reaches for it.

A person using any tool by hand — Midjourney, a pen, a camera — is making craft, and craft can be
calm. The moment something *automated* reaches for that same tool, you're back to the identity.md
objection, and the answer is "not Midjourney" again. The line isn't the tool; it's whose hand is on it.

## The two-hands rule (automation)

*Drafted 2026-06-24 — you lock.* The same line answers "can automation — Claude for Chrome, or any
agent — help, and still be calm?" It can, on one side only.

- **The creative hand stays human.** Generating, judging, rerolling, and picking are yours. Automating
  them re-crosses the line above: it rebuilds the fragile automated pipeline Article IX warns against (a
  browser bot breaks the moment the site changes, and is ToS-grey), reintroduces the reroll treadmill (a
  bot has no sense of *enough* — "received, not chased" needs a person to stop), and removes the very
  hands that make this calm.
- **The chore hand can be the machine.** Once you've chosen a keeper, the strict, tedious tail is exactly
  what the assistant should carry (loose human, strict machine): rename to the per-device convention,
  crop and export the device sizes, assemble the dynamic `.heic`, file it. Drafted, shown, confirmed —
  never silent (Article VII).
- **Prefer local over the browser.** Even for chores, driving a web UI is the fragile part; the export
  and packaging steps are local file operations and need no browser at all. Local beats browser
  automation on the Article IX durability test.

In short: the creative hand is human (choose, judge, stop); the chore hand may be the machine (rename,
export, package) — local, confirmed, never the generation.

---

## Constitution Check

1. **Serves:** IX (responsibly sourced — by removing the dependency entirely; the artifacts are plain
   files), VII (the two-hands rule keeps the creative act human, drafted-and-confirmed, never
   auto-executed), and the suite's "hands-on tools can be calm" reading.
2. **Violates:** none — this narrows, rather than overrides, identity.md's "not Midjourney" stance. A
   one-line clarification has been proposed back to identity.md (the person locks it).
3. **Subtracts:** removes any runtime dependency on an image API; the making is done before anything
   ships.
4. **Calm:** honest about the apparent conflict and names exactly where the line is, rather than
   quietly bending a locked doc.
