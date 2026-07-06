---
name: practical-guide
description: Draft or continue a practical-guide chapter or Substack piece in practical-guide mode — research-driven, anchored in lived expertise, minor author input requested only after research when a real gap needs it. Use when the user invokes /practical-guide or asks to write/edit a practical guide chapter or post.
---

# Practical Guide Mode

AI role: primary drafter, on a short leash. The author's lived expertise sets the spine; research fills in what she hasn't lived; her real input is pulled in only where a gap can't be closed any other way.

## Before drafting

1. Read `voice/CHEATSHEET.md`. Do not read the full `voice/book-voice.md` or `voice/tone-of-voice.md` unless a specific ambiguity needs a full section or a calibration sample (§9.3 is the approved practical-guide sample — pull it in only when checking a finished draft).
2. Read the relevant `projects/<slug>/project.md` for audience and premise. If none exists yet, point the user to `/new-project` first.
3. Identify, for the section being drafted, what's **lived** (she's done it — write with full confidence), what's **observed** (she's watched it in others — frame as noticing), and what needs **research** (frame as synthesis, never borrowed authority). This split is the single most important judgment call in this mode — get it wrong and the authority register breaks (book-voice.md §4).

## Research — delegate, don't dump

For anything in the "needs research" bucket:
- Spawn a subagent (`general-purpose` or a web-research-capable agent) to find and synthesize the specific claim, not to browse broadly. Ask it to return a short synthesis plus source citations — never raw search results or full page dumps into the main thread. This is the main token-cost lever in this mode: research volume happens in a subagent's disposable context, not this one.
- If a cited finding is widely repeated but methodologically contested, say so in the draft — that's in-voice (book-voice.md §4), not a hedge to avoid.
- Track sources per chapter so they can be listed at chapter end (light inline attribution, full references at the end — never footnote-heavy, never "studies show").

## Drafting

- Open with the earned principle, then show the reasoning (book-voice.md §5): "The most useful thing I've learned about X is…"
- Use simple filtering questions as a signature move where they fit naturally ("does this step actually require intelligence?").
- Self-aware asides that puncture false precision are in-voice — don't smooth them out.
- Route any technical material through a person: what someone did, decided, misjudged, learned (guards against book-voice.md §7 failure mode 2, consultant-speak).

## Author input — ask after, not before

Draft as far as research and lived material allow. Only pause to ask the author a question when:
- A claim needs to be lived-register but the draft doesn't actually know her experience of it, or
- Two plausible framings of her position exist and guessing wrong would misrepresent her.

Batch these into one short round of questions at the end of a drafting pass rather than interrupting mid-paragraph.

## Before delivering

Compare the draft against book-voice.md §9.3. Check against the forbidden list and failure modes in the cheatsheet. Flag anything that reads like it could sit unchanged on a vendor slide.

## Output

Save to `projects/<slug>/manuscript/`. Append or update the chapter-end reference list. Update the chapter log in `project.md`.
