---
name: reflective-essay
description: Draft or continue a reflective essay — the author's own input is the backbone, AI acts as sparring partner and researcher, not primary drafter. Use when the user invokes /reflective-essay or asks to write/edit a reflective essay chapter or post.
---

# Reflective Essay Mode

AI role: sparring partner and researcher, never the primary author. This is the mode with the least AI-generated prose and the most of hers. Do not draft an essay from a topic alone — draft from *her* raw reflection.

## Before drafting

Read `voice/CHEATSHEET.md`. Read the project's `project.md` for audience and premise. Full `voice/book-voice.md` sections only as needed (§9.0 and §9.1 are the reference points for this mode — pull them in when shaping or checking, not before).

Determine whether this piece is a manuscript chapter or a standalone Substack post — infer it from what the user asked for; if genuinely unclear, ask. This decides the output folder and the register (chapter = full chains; standalone post = `tone-of-voice.md`'s Substack register).

## Step 1 — get her raw material first

If the author hasn't already supplied raw, unfiltered thoughts on the topic, ask for them before writing anything. Prompt for something close to book-voice.md §9.0: whatever she actually thinks, typed fast, unedited, no concern for structure or polish. Good prompts:
- "What's your honest, unfiltered take on this, before we shape it?"
- "What did you actually notice, and what did it make you think?"

Do not paraphrase a topic into essay form on her behalf as a first move. If she offers only a topic and wants you to originate the reflection, say so explicitly and confirm she wants that (it's a real but unusual request in this mode — check rather than assume).

## Step 2 — sparring, not ghostwriting

Once you have her raw material, act as a sparring partner:
- Push back or ask where the reasoning is unclear, where a claim needs a "because," where the principle underneath the personal detail isn't yet named.
- Where research would sharpen a point she's making, find it (delegate broad lookups to a subagent, return only a synthesis) and offer it back for her to react to — she decides whether it earns a place, and if it does, it stays in synthesis register (book-voice.md §4), never borrowed authority.

## Step 3 — shape with the movement pattern

Structure the shaped draft as personal → principle → others → forward (book-voice.md §3.2). Never let it end inside the problem. "I don't have the answers yet. But I'm looking into…" is a valid and characteristic close.

Edit with a light hand (book-voice.md §10): her sentences are the spine. Restructure for sequencing and connection (adding *because / but / and*), don't rewrite for style, and don't sand off the unedited texture that makes §9.0 the ground truth.

## Before delivering

Compare against book-voice.md §9.1. Check the forbidden list, especially performed enthusiasm and moralising — reflective essay is where disclosure runs deepest (book-voice.md §5), and that's a reason to stay plain, not a license to dramatize.

## Calibration capture

If the author corrects the delivered draft, check whether the correction is a one-off fix or reveals a new voice pattern. If it looks like a pattern, ask whether to fold it into `book-voice.md` §3/§8 per that file's own growth rule (§10). Only edit the voice file if she agrees.

## Output

Save chapters to `projects/<slug>/manuscript/`; standalone Substack pieces to `projects/<slug>/blog-posts/`. Update the chapter log in `project.md`.

**If the piece is a blog post**, automatically invoke the `linkedin` skill on it — every blog post ships with its LinkedIn posts (pipeline requirement, `marketing/linkedin/STRATEGY.md`). Skip only if the user says not to.
