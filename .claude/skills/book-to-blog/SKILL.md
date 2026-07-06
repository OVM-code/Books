---
name: book-to-blog
description: Derive a Substack post from a book chapter or section, adapted to short-form voice, written to pique a reader's interest in the book. Use when the user invokes /book-to-blog or asks to turn a chapter into a blog post.
---

# Book → Blog

Take one self-contained beat from a manuscript chapter and adapt it to Substack length and register, ending with a genuine (not salesy) pull toward the book.

## Before drafting

Read `voice/CHEATSHEET.md`. Read the source chapter from `projects/<slug>/manuscript/` in full — you need to pick the right excerpt, not just the opening.

## Step 1 — pick the beat

Find the single strongest self-contained observation, reframe, or story-beat in the chapter — one that makes sense read in isolation, without the surrounding chapter. Don't try to compress the whole chapter; pick the part that already stands alone.

## Step 2 — register shift

Switch from book-voice chained reasoning to tone-of-voice short-form: compress, one idea, lead with the observation. Substack posts run longer than a LinkedIn post (roughly 300-900 words is normal, not 3-6 lines) — carry over tone-of-voice.md's core attributes and the pre-publishing filter, not its strict LinkedIn line-count structure.

## Step 3 — the pull toward the book

Tone-of-voice.md's LinkedIn structure ends on an open reflection, never a CTA. A Substack piece derived from a book is allowed one exception: a closing beat that honestly signals there's more — because there genuinely is a book behind it — without becoming a pitch. It should read like an honest continuation of the thought, not a sales tab. If it would sound at home under "buy now," it's off-voice; if it sounds like "here's where I take this further," it's fine.

## Before delivering

Run it against the Pre-Publishing Filter (tone-of-voice.md): true for her, written from a full state (flag if unsure — that's the author's call, not yours to guess), and does it leave the reader more clear or more themselves. Check it doesn't drift into listicle or hook-first structure.

## Output

Save to `projects/<slug>/blog-posts/`. Note in the file, and in `project.md`'s chapter log, which chapter it was derived from.

**Then, automatically:** invoke the `linkedin` skill on the finished post. Every blog post ships with its LinkedIn posts — this is a pipeline requirement (see `marketing/linkedin/STRATEGY.md`), not an optional extra. Skip only if the user explicitly says not to.
