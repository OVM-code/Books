---
name: linkedin
description: Generate LinkedIn posts (3, one per template family) from a blog post or chapter, aligned with the voice files and the LinkedIn strategy, and enter them into the posting queue. Use when the user invokes /linkedin on a piece, asks for LinkedIn posts from written material, or when another skill's pipeline step calls for it after producing a blog post.
---

# LinkedIn Posts from Written Material

Turn one finished piece into 3 LinkedIn posts, each on a different beat, each passing the voice filters, one designated as the funnel post. This skill also runs as the automatic last step of any skill that produces a blog post.

## Before generating

Read, in this order:
1. `voice/CHEATSHEET.md` — shared attributes and forbidden registers.
2. `marketing/linkedin/STRATEGY.md` — cadence, content mix, link policy, queue statuses.
3. The source piece in full (`projects/<slug>/blog-posts/` or `manuscript/`).
4. `voice/tone-of-voice.md`, LinkedIn sections — this is the ONE skill where the full short-form file earns its load every time: the three templates, the format rules, and the pre-publishing filter are the working material here.

Also glance at recent rows in `marketing/linkedin/queue.md`: if posts from the same source or on a near-identical beat already exist, tell the user instead of generating duplicates.

## Generating the 3 posts

**Find three genuinely different beats in the piece** — not the same insight paraphrased three ways. Followers may see all three in one week; each must feel like its own thought. If the piece truly contains only two distinct beats, generate two and say so — a forced third fails the "is this actually true for me" filter.

Map each beat to the template family it naturally is (don't force a beat into a template):
- **Observation** — the piece's concrete noticing, specific and real.
- **Honest Admission** — what she didn't know, got wrong, or is still sitting with.
- **Reframe** — the belief the piece pushes against and what she thinks instead.

**Format, per tone-of-voice.md:** 3–6 lines before a line break, one idea per post, open with the observation (never a question or hook), end on reflection or an open thought. Short sentences — this is the short-form register, not book chains.

**Pull from her sentences.** Where the piece contains a line that already works at post length, use it (minimal-touch principle: her sentences are the spine). Write new connective text only where needed.

**Designate the funnel post.** Exactly one of the three carries the link to the Substack piece: pick the beat that most naturally continues into the full piece. Frame the link as honest continuation ("I wrote about where this took me"), never as a CTA. The other two get no link and no pointer.

**Audience check:** the posts inherit the source piece's audience (`project.md`). Vocabulary and assumed context follow it.

## Self-check before delivering

Run each post against:
- The forbidden registers (cheatsheet + tone-of-voice avoid-table): no hooks, no listicle energy, no performed enthusiasm, no "here's the thing," no em-dashes.
- The pre-publishing filter: actually true for her (nothing claimed as lived that the source piece doesn't support), and does it leave the reader more clear or more themselves.
- Distinctness: would a follower who sees all three in a week feel they read three thoughts, or one thought three times?

## Output

1. Save all posts to `marketing/linkedin/posts/<piece-slug>.md`, each labeled with its template family and funnel designation, with a header noting the source piece path.
2. Append one row per post to `marketing/linkedin/queue.md`, status `drafted`.
3. Show the posts inline for review, and remind: publishing means flipping the queue row to `approved`/`posted` — and per the strategy, don't run all three in a row.

## When invoked on her own raw draft

If the source is something Olivia wrote herself (not generated), the same process applies but with an even lighter touch: her phrasing survives wherever it fits the format; edit for the 3–6 line structure, not for style.
