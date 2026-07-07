---
name: new-project
description: Scaffold a new book or blog-post-series project (folder, project.md brief). Use when the user wants to start a new book, a new standalone blog post series, or asks "set up a new project/book".
---

# New Project

Scaffold `projects/<slug>/` from `projects/_template/` and fill in its brief. This is the only skill that needs to ask setup questions; every other skill reads the answers back out of `project.md` instead of re-asking.

## Steps

1. Ask (in one message, only what isn't already obvious from context):
   - Working title
   - Starting point: a book from scratch, or a project that will begin life as Substack posts and grow into a book later
   - Primary mode: practical guide / reflective essay / story + insight / mixed
   - Audience: young professionals & students (18-28) / professional readers (AI, ERP, consulting)
   - One or two sentences on the working premise
2. Derive a kebab-case `<slug>` from the title and confirm it. Check whether `projects/<slug>/` already exists first — `cp -r` merges into an existing folder rather than failing, which can silently overwrite an in-progress `project.md`. If it exists, tell the user and ask whether they meant an existing project (point them at it instead) or want a different slug.
   ```
   cp -r projects/_template projects/<slug>
   ```
3. Fill in `projects/<slug>/project.md` with the answers — don't leave template placeholders.
4. Report back the path and tell the user which skill to invoke next: `/practical-guide`, `/reflective-essay`, or `/story-insight` for the declared mode. For a post-first project, tell them to draft the first post in that same mode skill, then use `/blog-to-book` later once there's enough material.

## Token-cost note

Do not read `voice/book-voice.md` or `voice/tone-of-voice.md` in full for this skill — scaffolding doesn't need the voice files at all, only the project brief.
