---
name: linkedin
description: Generate LinkedIn posts from a blog post or chapter (3, one per template family), or a single native post from something the user describes in the moment with no written source. Use when the user invokes /linkedin on a piece, asks for LinkedIn posts from written material, mentions something they noticed that would make a good post, or when another skill's pipeline step calls for it after producing a blog post.
---

# LinkedIn Posts

Two modes: **derived** (3 posts from an existing piece) and **native** (1 post from something the author tells you directly, no written source). Which one applies is usually obvious from how the skill was invoked — a piece path or "generate posts for X" means derived; "I noticed X today" or "post idea:" with no source file means native. If it's unclear, ask.

This skill also runs as the automatic last step of any skill that produces a blog post (derived mode only — that pipeline step always has a source piece).

## Native mode — no source piece

Native posts are roughly a third of the planned content mix (`marketing/linkedin/STRATEGY.md`) precisely because an account that only ever posts derived content stops reading like a person.

1. Ask what she noticed, if it isn't already in her message — concrete and specific, the same register as raw reflection elsewhere in this system. Don't invent detail she didn't give you.
2. Read `voice/tone-of-voice.md`'s LinkedIn section (this mode always needs the full templates, not the cheatsheet's summary — there's no piece to lean on).
3. Match it to whichever single template fits (Observation / Honest Admission / Reframe) — don't force one that doesn't.
4. This is a standalone post: there is no funnel post designation, no link. Native posts end on reflection or an open thought like any other.
5. Run the same self-check below, save to `marketing/linkedin/posts/native.md` (append, don't overwrite), and add one row to `queue.md` with Source piece = `native` and a short note on what it was about.

## Derived mode — from an existing piece

### Before generating

Read, in this order:
1. `voice/CHEATSHEET.md` — shared attributes and forbidden registers.
2. `marketing/linkedin/STRATEGY.md` — cadence, content mix, link policy, queue statuses.
3. The source piece in full (`projects/<slug>/blog-posts/` or `manuscript/`).
4. `voice/tone-of-voice.md`, LinkedIn sections — this is the ONE skill where the full short-form file earns its load every time: the three templates, the format rules, and the pre-publishing filter are the working material here.

Also glance at recent rows in `marketing/linkedin/queue.md`: if posts from the same source or on a near-identical beat already exist, tell the user instead of generating duplicates.

### Generating the 3 posts

**Find three genuinely different beats in the piece** — not the same insight paraphrased three ways. Followers may see all three in one week; each must feel like its own thought. If the piece truly contains only two distinct beats, generate two and say so — a forced third fails the "is this actually true for me" filter.

Map each beat to the template family it naturally is (don't force a beat into a template):
- **Observation** — the piece's concrete noticing, specific and real.
- **Honest Admission** — what she didn't know, got wrong, or is still sitting with.
- **Reframe** — the belief the piece pushes against and what she thinks instead.

**Format, per tone-of-voice.md:** 3–6 lines before a line break, one idea per post, open with the observation (never a question or hook), end on reflection or an open thought. Short sentences — this is the short-form register, not book chains.

**Pull from her sentences.** Where the piece contains a line that already works at post length, use it (minimal-touch principle: her sentences are the spine). Write new connective text only where needed.

**Designate the funnel post.** Exactly one of the three carries the link to the Substack piece: pick the beat that most naturally continues into the full piece. Frame the link as honest continuation ("I wrote about where this took me"), never as a CTA. The other two get no link and no pointer.

**Audience check:** the posts inherit the source piece's audience (`project.md`). Vocabulary and assumed context follow it.

### Self-check before delivering (both modes)

Run each post against:
- The forbidden registers (cheatsheet + tone-of-voice avoid-table): no hooks, no listicle energy, no performed enthusiasm, no "here's the thing," no em-dashes.
- The pre-publishing filter: actually true for her (nothing claimed as lived that the source piece doesn't support, or that she didn't actually tell you in native mode), and does it leave the reader more clear or more themselves.
- Distinctness (derived mode only): would a follower who sees all three in a week feel they read three thoughts, or one thought three times?

### Output (derived mode)

1. Save all posts to `marketing/linkedin/posts/<piece-slug>.md` — `<piece-slug>` is the source file's name without its extension (CLAUDE.md's pipeline invariants), so it matches whatever `/promote` looks up later. Each post is labeled with its template family and funnel designation, with a header noting the source piece path.
2. Append one row per post to `marketing/linkedin/queue.md`, status `drafted`.
3. Show the posts inline for review, and remind: publishing means flipping the queue row to `approved`/`posted` — and per the strategy, don't run all three in a row.

### When invoked on her own raw draft

If the source is something Olivia wrote herself (not generated), the same process applies but with an even lighter touch: her phrasing survives wherever it fits the format; edit for the 3–6 line structure, not for style.
