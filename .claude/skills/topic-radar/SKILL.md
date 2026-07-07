---
name: topic-radar
description: Research what people are actually searching for, asking about, and struggling with online, and turn that demand into a ranked list of topic opportunities Olivia can authentically write about. Use when the user invokes /topic-radar or asks what to write about next, what's in demand, or wants topic/market research for content.
---

# Topic Radar

Find real demand, then filter it through what Olivia can authentically write. The output is a ranked opportunity report, not a list of trending keywords — a topic only makes the report if there's evidence people are looking for it AND she has lived/observed ground to stand on (or a clear path to get it).

## Before researching

1. Read `voice/CHEATSHEET.md` (for the authenticity filter and audience profiles — not for drafting).
2. Check `marketing/linkedin/queue.md` for rows with `Resonated? = yes` — note which themes/topics they trace back to (via Source piece). This is real signal about what already worked, not a guess, and should raise those themes' ranking below if the current scan touches them. If the queue has no resonance data yet (too early, or the review loop hasn't run), skip this step; don't block the scan on it.
3. Ask, in one short message, only what isn't clear from context:
   - Which audience is this scan for: young professionals/students (18-28), professional readers (AI/ERP/consulting), or both?
   - Any theme seed ("around AI and learning", "around use-case assessment") or fully open?
   - Is this feeding an existing project (check `projects/*/project.md`) or hunting for new ones?

## Research — fan out, synthesize, cite

Delegate ALL of this to parallel subagents; each returns a short synthesis with citations, never raw dumps. Run one subagent per angle (a multi-modal sweep — each angle finds things the others miss):

1. **Questions people ask.** Reddit, Quora, HN, relevant forums: what is the target audience asking about in this theme? Recurring phrasings, unanswered or badly-answered questions, emotional undertones (overwhelm, feeling behind, distrust of hype).
2. **Search demand.** How people phrase the problem in search: question formulations, "how do I", comparison queries. Note the exact wording — it matters for /promote later.
3. **What's already being written.** Substack and LinkedIn writers in the adjacent space: what's saturated, what's covered only in hollow/thought-leader register (an opening for her — her differentiator is honesty and receipts where others perform), what's genuinely missing.
4. **Comment-section gaps.** On popular posts in the niche: what do commenters ask that the post didn't answer? Comments are demand that the existing supply provably failed to meet.

If the scan is for both audiences, run the sweep per audience — their questions barely overlap. This roughly doubles the research (8 subagents instead of 4); say so before running rather than letting the cost be a surprise.

## The authenticity filter (what makes this hers)

Raw demand is not enough. For each candidate topic, assess against the voice files:

- **Ground:** can she write this from lived or observed ground (book-voice.md §4)? If it would require borrowed authority throughout, drop it or flag it as "needs her input first."
- **Angle fit:** does it connect to her positioning — "use AI to become more yourself," staying in control of who you're becoming, effort as where value comes from? A topic in demand but off-positioning dilutes the brand.
- **The tone-of-voice.md test:** "Advice I haven't actually lived yet" and "hot takes on topics without real experience" are not-posts, no matter how much demand exists.

## Output — the opportunity report

Write to `marketing/radar/YYYY-MM-DD-<theme>.md` (today's date, short theme slug):

```
# Topic Radar — <theme> — <date>
Audience(s) scanned: …

## Ranked opportunities
For each (best first):
### <working topic title, plain, no clickbait>
- Demand evidence: what people are asking/searching, with 1-2 verbatim phrasings and sources
- The gap: why existing content isn't answering it (saturated-but-hollow / missing / badly framed)
- Her edge: which lived/observed material makes this hers to write
- Mode fit: practical guide / reflective essay / story + insight — and why
- Channel: book chapter candidate, standalone Substack post, or both
- Search phrasing to remember: exact wordings for /promote to reuse

## Dropped candidates (one line each: topic + why it failed the filter)

## Sources
```

Rank by demand strength × her edge, and nudge upward anything that overlaps a theme already marked `Resonated? = yes` in the queue (note this explicitly next to the opportunity when it applies, so the ranking reasoning is visible). Include the dropped list — knowing what was rejected and why prevents re-researching it next scan.

## After the report

Tell the user the top 2-3 opportunities in one or two sentences each and which skill to invoke to act on one (`/new-project` for a fresh project, or the mode skill directly for an existing one). Don't start drafting — that's the mode skills' job, invoked when she chooses.
