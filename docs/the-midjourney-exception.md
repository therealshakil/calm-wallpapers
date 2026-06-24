# The Midjourney exception

The suite's [identity](https://github.com/shakilclark/calm/blob/main/docs/identity.md) says, plainly,
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

---

## Constitution Check

1. **Serves:** IX (responsibly sourced — by removing the dependency entirely; the artifacts are plain
   files), and the suite's "hands-on tools can be calm" reading.
2. **Violates:** none — this narrows, rather than overrides, identity.md's "not Midjourney" stance. A
   one-line clarification has been proposed back to identity.md (the person locks it).
3. **Subtracts:** removes any runtime dependency on an image API; the making is done before anything
   ships.
4. **Calm:** honest about the apparent conflict and names exactly where the line is, rather than
   quietly bending a locked doc.
