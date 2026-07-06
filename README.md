# Books

A writing system for producing books and Substack posts in Olivia Vanmalleghem's voice, across three modes, with Claude Code doing a different job depending on which one you're in.

## The three modes

| Mode | What you bring | What AI does |
|---|---|---|
| **Practical guide** | Lived expertise, corrections after a draft exists | Primary drafter: researches, writes, anchors claims in the lived/observed/researched register |
| **Reflective essay** | Your own raw, unfiltered input, first | Sparring partner and researcher: pushes back, sharpens, finds supporting research, shapes with a light hand |
| **Story + insight** | The real material, drawn out through questions | Interviewer first, writer second: never invents a scene, lets the reframe you actually used carry the insight |

The same distinction carries into the blog pipeline: a book chapter can become a Substack post (`/book-to-blog`), and a post can grow into a chapter later (`/blog-to-book`), in whichever of the three modes it's headed toward.

## Layout

```
voice/
  CHEATSHEET.md     condensed voice reference — read by default
  book-voice.md     long-form authority (books, essays, chapters)
  tone-of-voice.md  short-form authority (Substack, LinkedIn, comments)

projects/
  _template/        blank scaffold, copied by /new-project
  <slug>/
    project.md      brief: mode, audience, premise, chapter/post log
    manuscript/      chapter drafts
    research/        synthesized research notes, sources at file end
    blog-posts/      Substack drafts derived from or feeding into the book

marketing/
  radar/            dated topic-opportunity reports from /topic-radar
  campaigns/        per-piece distribution plans from /promote
  linkedin/
    STRATEGY.md     what LinkedIn is for, cadence, content mix, link policy
    queue.md        posting queue: drafted → approved → posted / dropped
    posts/          generated LinkedIn posts, one file per source piece

.claude/skills/     one skill per mode + pipeline direction (see below)
CLAUDE.md           thin router Claude reads at session start
```

Every book or post series gets its own folder under `projects/`. A project can start as a book or as a run of posts — `project.md` tracks which, plus the mode and audience it's written for, so you only answer those questions once.

## Skills — what to invoke, and when

- **`/new-project`** — start a new book or post series. Asks for title, starting point, mode, audience, premise, and scaffolds the folder.
- **`/practical-guide`** — draft or continue practical-guide material. Splits what you've lived from what needs research, delegates web lookups to a subagent (so search noise never fills up this conversation), and only asks you questions after a real gap shows up.
- **`/reflective-essay`** — draft or continue a reflective essay. Always starts by asking for your raw, unfiltered take before writing anything, then acts as a sparring partner to sharpen it.
- **`/story-insight`** — draft or continue a story + insight piece. Runs a short guided-question sequence to recover the real scene and the reframe you actually used, before any prose gets written.
- **`/book-to-blog`** — turn a manuscript chapter into a Substack post. Picks the one beat that stands alone, shifts register to short-form, and ends with an honest nod toward the book rather than a pitch.
- **`/blog-to-book`** — grow a Substack post into a book chapter. Uncompresses short-form beats into the chained, reasoning-bearing sentences long-form uses, in whichever mode the project is set to.
- **`/topic-radar`** — research what people are actually asking and searching for online (forum questions, search phrasings, gaps in existing content, unanswered comment sections), then filter that demand through what Olivia can authentically write from lived or observed ground. Produces a ranked opportunity report in `marketing/radar/`, including the exact phrasings seekers use.
- **`/promote`** — take a finished post or chapter and build its distribution plan: title/subtitle options that carry the seeker's own words without turning into clickbait, Substack preview text and Notes angles, and a keyword note. Saves to `marketing/campaigns/`, reusing radar findings and already-generated LinkedIn posts when they exist.
- **`/linkedin`** — generate 3 LinkedIn posts from any piece: one per template family (Observation / Honest Admission / Reframe), each on a different beat so they don't repeat, exactly one carrying the link back to Substack (the funnel post). Posts land in `marketing/linkedin/posts/` and enter the queue as `drafted`. This skill also runs **automatically** as the last step whenever `/book-to-blog` or a mode skill finishes a blog post — every blog post ships with its LinkedIn posts.

Each skill file is the complete instructions for that job. `CLAUDE.md` doesn't repeat them — it just points here so idle context stays cheap.

## Voice files — how they relate

`book-voice.md` and `tone-of-voice.md` can conflict (short-form's "always write shorter" doesn't hold at book length). `book-voice.md` §1 states the precedence: it wins for anything book-length; `tone-of-voice.md` wins for posts and comments. `CHEATSHEET.md` is a distillation of both, meant to be read on nearly every turn; the two full files are for resolving a genuine ambiguity or checking a finished draft against the approved calibration samples in `book-voice.md` §9.

## A typical flow

1. `/topic-radar` — when planning what to write next, scan real online demand and get ranked, authenticity-filtered topic opportunities.
2. `/new-project` — set up the folder, declare mode and audience.
3. Draft chapters with the matching mode skill (`/practical-guide`, `/reflective-essay`, or `/story-insight`), one at a time, updating the chapter log in `project.md` as you go.
4. When a chapter has a beat worth surfacing early, `/book-to-blog` it into `blog-posts/` — its LinkedIn posts are generated automatically in the same run and queued in `marketing/linkedin/queue.md`.
5. When a post (yours or one that started independently) has more in it than the short form could hold, `/blog-to-book` it into a new manuscript chapter.
6. `/promote` — when a piece is ready to publish, build its distribution plan so the people the radar found actually encounter it.
7. Publish per `marketing/linkedin/STRATEGY.md`: 2–3 posts a week from the queue, one funnel post per source piece, flipping queue rows to `posted` as you go. Wrote a post yourself, outside the pipeline? Run `/linkedin` on it directly.

## Why it's built this way (token cost)

- `CLAUDE.md` is a router, not a rulebook — it costs almost nothing to keep loaded.
- Skills load in full only when you invoke them, and only the relevant one loads at a time.
- `CHEATSHEET.md` covers most drafting and self-checking decisions cheaply; the full voice files open only when a skill says it's actually needed.
- Research is delegated to subagents that return a synthesis and citations — raw search results and fetched pages never land in the main conversation.
