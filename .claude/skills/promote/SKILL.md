---
name: promote
description: Build a distribution plan for a finished piece — titles, framing, keywords, Substack packaging, and a LinkedIn post — so the people already looking for it can find it. Use when the user invokes /promote or asks how to market, distribute, title, or get readers for a post or chapter.
---

# Promote

Take something already written and package it so it reaches the people who are searching for exactly this. Channels: Substack and LinkedIn. The constraint that makes this hers: the packaging must pass the same voice filters as the writing — no clickbait, no hooks, no performed enthusiasm. Findability comes from *matching the reader's own words*, not from louder framing.

## Before planning

1. Read `voice/CHEATSHEET.md` and the finished piece (from `projects/<slug>/blog-posts/` or `manuscript/`).
2. Check `marketing/radar/` for a recent report covering this topic — if one exists, reuse its "search phrasing to remember" instead of re-researching.
3. Check `projects/<slug>/project.md` for the audience — it decides vocabulary everywhere below.

## Research — how seekers phrase it

If no usable radar report exists, delegate to a subagent: find the exact words the target audience uses when looking for what this piece answers — question phrasings, problem descriptions, the vocabulary gap between how she'd say it and how a stranger would search it. Synthesis + citations back, no raw dumps.

## Output — the campaign file

Write to `marketing/campaigns/<piece-slug>.md`:

**1. Title + subtitle options (3-4).**
Each must contain the seeker's own phrasing somewhere AND read as her voice. Test each against the forbidden registers: no "unlock", no listicle framing, no rhetorical-question hooks, no overpromising. Plain observation that happens to contain the searched-for words beats a clever hook. Mark which option you'd pick and why.

**2. Substack packaging.**
- One-paragraph post description/preview text (this is what shows in inboxes and the app — lead with the observation).
- 2-3 Substack Notes angles: short, self-contained excerpts or restatements from the piece that stand alone as Notes and link back. Pull real sentences from the piece where possible (minimal-touch principle) rather than writing new marketing copy.
- Tags/topics to file it under, using the researched vocabulary.

**3. LinkedIn posts.**
Don't write these here — the `linkedin` skill owns LinkedIn generation. Check `marketing/linkedin/posts/<piece-slug>.md`: if the piece's posts already exist (they should, the pipeline generates them when a blog post is finished), reference them and note in the campaign file which one is the funnel post and where it sits in `marketing/linkedin/queue.md`. If they don't exist yet, invoke the `linkedin` skill now.

**4. Keyword note.**
The 5-10 exact phrasings seekers use, for reuse: future titles, Substack tags, and so the same research isn't redone next time. Cross-reference the radar report if one fed this.

**5. Timing/sequencing note (short).**
Suggested order: Substack post → Notes over following days → LinkedIn post. Flag if the piece pairs with another published piece worth cross-linking.

## The filter, applied to marketing

Before delivering, run the packaging itself through tone-of-voice.md's pre-publishing filter. Marketing copy is still her voice in public: if a title sounds good but she wouldn't say it, it fails. When a demand-matching phrase and her natural phrasing conflict, keep her phrasing in the piece and use the seeker's phrasing in the title/tags/description — the metadata is where matching happens, the writing is where the voice lives.

## After

Update `project.md`'s chapter log (add a "promoted" note or column entry for the piece). Summarize the recommended title and the LinkedIn post inline so she can act without opening the file.
