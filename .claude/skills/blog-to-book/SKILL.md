---
name: blog-to-book
description: Expand a Substack post (or a short run of related posts) into a book-length chapter or section, adding the reasoning, research, and structure the short form didn't have room for. Use when the user invokes /blog-to-book or asks to grow a post into a chapter.
---

# Blog → Book

Take short-form material that already exists and grow it into long-form, in whichever of the three modes it's becoming.

## Before drafting

Read `voice/CHEATSHEET.md`. Read the source post(s) from `projects/<slug>/blog-posts/` in full. Check `project.md` for the project's declared mode and audience — if this post is starting a new project rather than joining an existing one, run `/new-project` first to establish that.

## Step 1 — determine the target mode

If not already set in `project.md`, ask which of the three modes this is becoming (practical guide / reflective essay / story + insight) — the expansion path differs by mode:

- **→ practical guide:** the post's observation becomes the earned principle the chapter opens with; expand with research (delegate lookups to a subagent, save synthesis to `projects/<slug>/research/<topic-slug>.md`) and route technical material through people, per `practical-guide` skill.
- **→ reflective essay:** treat the post itself as raw material, equivalent to a book-voice.md §9.0 sample, and shape it with the movement pattern (personal → principle → others → forward), per `reflective-essay` skill. Ask the author for anything the post compressed away that she now remembers wanting to say.
- **→ story + insight:** the post likely only has room for the reframe, not the full scene. Run the guided elicitation from the `story-insight` skill to recover the fuller sequence before writing.

## Step 2 — expand the mechanics, not just the length

The core move is book-voice.md §2: uncompress short-form beats into chained reasoning (*because / but / and / as*), give each idea its own paragraph instead of its own post-length compression, and let the ending turn outward and forward rather than stopping where the post stopped.

## Before delivering

Compare against the relevant sample in book-voice.md §9 for the target mode. Check for rhythmic monotony (§7) if several posts are being merged into one chapter — merged material is where identical chain shapes tend to pile up.

## Output

Save to `projects/<slug>/manuscript/`. Update the chapter log in `project.md`, noting which post(s) it grew from.
