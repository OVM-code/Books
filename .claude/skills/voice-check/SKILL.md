---
name: voice-check
description: Audit a batch of manuscript chapters or blog posts together for voice drift that a single piece's own self-check can't see — rhythmic monotony across sessions, forbidden phrases creeping back in, authority-register slips, audience bleed between chapters. Use when the user invokes /voice-check, asks for a voice or consistency audit, or before a milestone (finishing a draft, publishing a batch).
---

# Voice Check

Every mode skill self-checks the piece it just wrote, in isolation. That catches everything a single draft can fail at, but not what only shows up *across* several pieces written in different sessions: book-voice.md §7 names rhythmic monotony and consultant-speak drift as failure modes that specifically compound "over 200 pages" — no per-chapter check can see that compounding, because each chapter looks fine alone. This skill is the cross-piece pass.

This is a periodic health check, not a per-draft gate. Run it every several chapters, before a publishing milestone, or whenever asked — not after every single piece (that's what each mode skill's own "before delivering" step is for).

## Before checking

1. Read `voice/CHEATSHEET.md`.
2. Read the project's `project.md` for declared mode and audience per chapter.
3. Determine scope: default to every file in `projects/<slug>/manuscript/`; the user may narrow it to a chapter range or to `blog-posts/`. Say how many files are in scope before running — this is a batch operation and the user should know its size.

## Extraction (delegate per file)

For anything beyond a small handful of files, spawn one subagent per file (parallel) rather than reading everything into the main thread. Each subagent reads one chapter/post and returns a compact structured signal, not the chapter text:
- Chain-shape sample: 2-3 example sentences and whether the paragraph runs a uniform because/but/and shape throughout.
- Any forbidden-register hits with the exact quote (em-dashes, triadic listing, "it's not X it's Y", emotional vocabulary substituting for reasoning, rhetorical-question hooks, thought-leader phrasing).
- The chapter's closing lines (to check it turns forward, not inside the problem).
- Any full-confidence claim ("this is how I...", "I've learned that...") on a topic that reads like it needed research rather than lived experience — flag as a possible authority-register slip, don't assume.
- Declared or apparent audience, and any vocabulary that seems to assume the *other* audience's context.

## Synthesis (main thread, across all signals)

Compare the returned signals across files for:
- **Rhythmic monotony:** three or more chapters/pieces in a row with the same chain shape and no short plain sentence landing after a long chain anywhere.
- **Forbidden-register creep:** any hit at all is worth surfacing, even a single em-dash — the ban is global, not "rare is fine." Also flag a device like "it's not X, it's Y" if it appears in more than one chapter even though each individual chapter might only use it once (book-voice.md's "once per chapter at most" is a per-chapter cap, not a license to make it a running device across chapters).
- **Ending-inside-the-problem:** any chapter whose closing lines stop on a difficulty rather than turning outward or forward.
- **Authority-register slips:** flagged full-confidence claims — cross-check against what the author has actually said elsewhere in the project (research files, prior chapters) before concluding it's a slip; if genuinely unclear, list it as "needs the author's confirmation" rather than asserting it's wrong.
- **Audience bleed:** vocabulary or assumed context in a chapter that doesn't match its declared audience, or drifts partway through a piece.

## Output

Write (overwrite) `projects/<slug>/VOICE-CHECK.md`:

```
# Voice Check — <project> — <date>
Scope: <N files, path range>

## Findings (most concerning first)
### <issue type>
- Where: <file(s), quote or description>
- Why it matters: <which book-voice.md section this violates>
- Suggested fix: <specific, e.g. "vary the chain length in paragraph 3" or "confirm whether this claim is lived or needs research framing">

## Clean
<files/patterns checked with nothing to report — a short list, so a clean run is visibly clean, not just silent>
```

Don't edit any chapter yourself. This skill reports; the author (or a follow-up mode-skill invocation) decides what to change; this keeps minimal-touch editing (book-voice.md §10) intact — a batch audit is exactly the kind of pass that tempts wholesale rewriting, and that's not this skill's job.

## After

Tell the user the count of findings by severity and ask whether to fix them now (by re-invoking the relevant mode skill on the affected chapter) or leave the report for later.
