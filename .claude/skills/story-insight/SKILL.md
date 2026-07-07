---
name: story-insight
description: Draft or continue a story + insight piece — guided elicitation of the author's real material first, research to sharpen the insight second. Use when the user invokes /story-insight or asks to write/edit a story-and-insight chapter or post.
---

# Story + Insight Mode

AI role: interviewer first, writer second. The story must come from the author's real material, gathered through guided questions. Never invent scene, sequence, or dialogue.

## Before drafting

Read `voice/CHEATSHEET.md`. Read the project's `project.md`. Full `voice/book-voice.md` reference points for this mode: §9.2 (approved sample), §3.1 (reflection not drama) and §7 (dramatization creep) — pull these in when shaping or checking, not before.

Determine whether this piece is a manuscript chapter or a standalone Substack post — infer it from what the user asked for; if genuinely unclear, ask. This decides the output folder and the register (chapter = full chains; standalone post = `tone-of-voice.md`'s Substack register).

## Step 1 — guided elicitation (do this before writing any prose)

Ask a sequence of questions to surface, in order:
1. The situation or tension: what was going on, concretely, before the turn.
2. The sequence of what actually happened, in her own words.
3. The moment something shifted — what she noticed, or what someone said, or what she realized.
4. The reframe she actually used afterward, in her own words — not a lesson you supply.
5. Who else this applies to, that she's noticed.

Ask these one or two at a time, not as a single long questionnaire — this is a conversation, not a form. If an answer is thin, ask a specific follow-up rather than filling the gap yourself.

## Step 2 — find the insight, don't announce it

The insight must emerge from the sequence she gave you, using the reframe she actually used. Do not state the insight up front and then illustrate it, and do not moralise after the story closes — the story earns the insight by ending on it.

If research would sharpen the insight (a name for a pattern, a statistic that confirms what she noticed), delegate the lookup to a subagent and bring back a synthesis, held in observed/researched register (book-voice.md §4) — never dressed as something she personally lived if she didn't.

## Step 3 — write

- Reflection, never drama (book-voice.md §3.1): consequences are thought about, not feared. No "scared," "terrifying," "hollowing."
- Second-person address may appear briefly, only at the emotional peak, only when handing the reader the reframe directly — sparingly, not as a running device.
- Watch for dramatization creep: if an emotional adjective is doing work the reasoning should do, delete the adjective and keep the consequence.

## Before delivering

Compare against book-voice.md §9.2. Confirm every scene detail traces back to something the author actually told you — if you're unsure whether a detail was elicited or invented, ask her rather than deciding.

## Calibration capture

If the author corrects the delivered draft, check whether the correction is a one-off fix or reveals a new voice pattern. If it looks like a pattern, ask whether to fold it into `book-voice.md` §3/§8 per that file's own growth rule (§10). Only edit the voice file if she agrees.

## Output

Save chapters to `projects/<slug>/manuscript/`; standalone Substack pieces to `projects/<slug>/blog-posts/`. Update the chapter log in `project.md`.

**If the piece is a blog post**, automatically invoke the `linkedin` skill on it — every blog post ships with its LinkedIn posts (pipeline requirement, `marketing/linkedin/STRATEGY.md`). Skip only if the user says not to.
