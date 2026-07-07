# Books

Olivia Vanmalleghem's writing system: books and Substack posts, in her own voice, across three modes.

## Layout

- `voice/` — voice authority. `CHEATSHEET.md` (read this by default), `book-voice.md` (long-form authority), `tone-of-voice.md` (short-form/LinkedIn authority).
- `projects/<slug>/` — one per book or post series: `project.md` (brief: mode, audience, premise, chapter log), `manuscript/`, `research/`, `blog-posts/`.
- `projects/_template/` — scaffold copied by `/new-project`.
- `marketing/` — demand research and distribution. `radar/` (dated topic-opportunity reports from `/topic-radar`), `campaigns/` (per-piece distribution plans from `/promote`), `linkedin/` (STRATEGY.md, queue.md, posts/ — generated LinkedIn posts).

## Skills (each is the full instructions for its job — this file stays thin on purpose)

- `/new-project` — start a new book or post series; writes `project.md`.
- `/practical-guide` — research-driven chapters/posts, AI as primary drafter on lived-expertise ground, minor author input requested only after research when needed.
- `/reflective-essay` — author's own input is the backbone, AI as sparring partner and researcher.
- `/story-insight` — guided elicitation of the author's real story material first, research second.
- `/book-to-blog` — derive a Substack post from a manuscript chapter, to pull readers toward the book.
- `/blog-to-book` — grow a Substack post into a book chapter.
- `/topic-radar` — research online demand (questions, searches, content gaps) into a ranked, authenticity-filtered topic report.
- `/promote` — distribution plan for a finished piece: titles, Substack packaging, seeker-phrasing keywords.
- `/linkedin` — 3 LinkedIn posts (one per template, one funnel post) from any piece, or 1 native post from something told to Claude directly. Runs automatically whenever a skill finishes a blog post.
- `/voice-check` — batch audit across several manuscript chapters or posts for drift a single piece's own self-check can't see. Periodic, not per-draft.

## Persistence

This runs in an ephemeral remote container — uncommitted work does not survive a reclaimed session. After producing or updating any file (a draft, a queue row, a report), say what changed and ask whether to commit and push now. Don't commit automatically without asking, but don't let a session end on unsaved work either — the ask itself is the safety net.

## Pipeline invariants

- Any skill that writes a new file into a project's `blog-posts/` folder must invoke the `linkedin` skill on it before finishing, unless the user says not to. This is stated in each mode skill and in `book-to-blog`; it's repeated here as a backstop in the file that's always loaded.
- `<piece-slug>` (used by `linkedin`, `promote`, and the campaigns/posts folders) is always the source file's name without its extension — e.g. `blog-posts/ai-use-case-assessment.md` → `ai-use-case-assessment`. Every skill that reads or writes a slug-named file uses this same derivation so they resolve to the same filename.

## Token-cost principles

- Don't load both full voice files for routine work. `voice/CHEATSHEET.md` covers the vast majority of drafting and checking decisions; open `book-voice.md` or `tone-of-voice.md` in full only for a genuine ambiguity or a calibration-sample comparison.
- Delegate research (web lookups, source gathering) to subagents. They return a synthesis and citations, not raw dumps — search results and fetched pages stay out of the main conversation.
- Each writing mode lives in its own skill file, loaded only when invoked. Don't inline mode-specific instructions here.
