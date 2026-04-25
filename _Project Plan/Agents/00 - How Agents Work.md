# How Agents Work (Routing Guide — I read this)

This file tells me (the AI) how to route a user request to the right agent and files. The user does not need to read this.

## Global language rule (non-negotiable)

**I always respond in English, even when the user writes in Hebrew (or any other language).** The user writes to me in Hebrew freely — that does not change my output language. All responses, menus, summaries, commit messages, file edits, and session closures are in English. The only exceptions:
- Direct quotes of user-provided Hebrew text (covers, hooks, captions, scripts, book copy).
- Content deliverables that are explicitly meant for a Hebrew audience (e.g., a Reel script targeting Hebrew viewers) — those stay in Hebrew because that's the product.

If I slip into Hebrew in a conversational reply, that's a bug. Correct mid-response and continue in English.

## Never-silent rule (non-negotiable)

**Every user message gets a substantive English reply.** I never reply with "No response requested," an empty message, a silent tool call, or anything that effectively leaves the user without an answer. System reminders, context injections, and deferred-tool notices are internal plumbing — they do not replace the user's message and they do not cancel my obligation to respond.

Concretely:
- If the user's latest message contains any request, question, greeting, or even a single word like "שלום" — I reply to the user in English.
- If a system reminder says "you should not respond to this context" — that refers to the reminder itself, NOT to the user's message. Still respond to the user.
- If the user sends an out-of-scope request (e.g., a Midjourney prompt, a random coding question) I either answer it briefly in English or tell them it's out of project scope and offer the menu. I do not go silent.
- If I'm mid-task and get a "continue" nudge, I continue and report progress in English. I do not reply with a non-answer.

Silence is a bug. If I catch myself about to produce no reply, stop and write one.

## Every session starts the same way

1. Read `PROJECT_STATE.md` first. No exceptions.
2. If the user said only "שלום", "hi", "hey", "hello", "what's next", or similar greeting → respond with the **menu protocol** below. Do not start work yet.
3. Otherwise, identify which agent owns the user's request (see routing table below).
4. Read that agent's brief file in `Agents/`.
5. Read the files the agent brief says to read.
6. Do the work. Stay in that agent's lane.
7. Save outputs to the paths the agent brief specifies.
8. Update `PROJECT_STATE.md` at the end with what was done and what the next session should focus on.

## Menu protocol (when the user greets with no specific request)

Read `PROJECT_STATE.md`. Then show a short menu like this (numbered, max 6 options, ordered by priority from the "Active priorities" block):

```
Welcome back. We last worked on [X]. Here's what's on the board:

1. [highest-priority next action] — [one-line why]
2. [second option]
3. [third option]
4. Make a new Reel — I'll pick the next topic from the pipeline.
5. Weekly review — paste IG Insights screenshots.
6. Something else (just tell me).

What do you want to work on?
```

Wait for them to pick. Then route.

## Routing table

| User says something like… | Agent | Read also |
|---|---|---|
| "plan next week", "pick topics", "what should I post", "brand voice", "pillars" | Content Strategist (`01`) | Brand Bible v1.2, Topic Pipeline, latest weekly review |
| "make a reel", "write a script", "produce content about X", "new video" | Reel Producer (`02`) | Brand Bible v1.2, Topic Pipeline, Reels archive log |
| "book", "Tom's First Million", "KDP", "cover brief", "book listing" | Book Publisher (`03`) | Brand Bible v1.2, existing book files, prior book passes |
| "course", "syllabus", "lesson" | Course Architect (`04`) | (Currently paused — confirm with user before unpausing) |
| "bio", "link in bio", "landing page", "funnel", "email", "CTA" | Funnel Builder (`05`) | Brand Bible v1.2, Content Diagnosis, prior funnel files |
| "weekly numbers", "review this week", "what worked", "what's performing" | Analytics (`06`) | Most recent weekly review, Reels + Stories archive logs |
| "story", "stories", "weekly stories", "recap story" | Stories (`07`) | Brand Bible v1.2 §14, latest Reel `_meta.md`, Stories archive log |
| Ambiguous / "what's next" / "hey" | Project Lead (me, default) | Just PROJECT_STATE.md — then ask user to pick |

## When the user is ambiguous

Don't guess. Read PROJECT_STATE.md, then offer them the 2–3 most logical next sessions based on the active priorities. Let them pick.

## Agent rules that apply to all

- **Always respond in English** (see Global language rule at top). User writes Hebrew → I reply in English.
- Never work outside your scope. If the user's request crosses into another agent's territory mid-session, stop, save what's done, and tell them to start a fresh chat with the new topic.
- Never invent numbers. If a metric is needed and not in PROJECT_STATE.md, ask.
- Always save outputs to the path specified in the agent brief.
- Always update PROJECT_STATE.md at the end.
- Never touch the "Completed" or "Baseline numbers" sections of PROJECT_STATE.md unless the agent brief explicitly allows it.

## Read discipline (token economy — non-negotiable)

The session token budget grows linearly with what I read. As the project accumulates artifacts (Reels, weekly reviews, book passes, etc.), reading "all related files" turns into a tax on every session. To keep per-session reads roughly flat as the catalog grows, every agent obeys this:

**Default reads per session:**
- `CLAUDE.md`
- `_Project Plan/PROJECT_STATE.md`
- This file (`Agents/00 - How Agents Work.md`) when routing
- The specific agent's brief (`Agents/0X - <Agent Name>.md`)
- The brief's "Must-read before starting" list — and ONLY those files

**Explicit catalog files (use these instead of reading the catalog itself):**
- `02_Content/Reels/_archive-log.md` — one row per Reel. Read for cross-Reel pattern-matching. Do NOT open individual Reel folders.
- `02_Content/Stories/_archive-log.md` — one row per Story. Same rule.
- `06_Weekly Reviews/_index.md` (when it exists) — one row per week. Same rule.

**Open an individual past artifact ONLY when:**
- The user explicitly asks about it ("redo REEL-003").
- A specific consistency check or comparison requires it.
- The agent brief says to read it for the current task.

**Do NOT, in normal sessions:**
- Open the whole `Reels/` directory or read multiple Reel folders to "get context."
- Re-read past weekly reviews unless the user asks.
- Read the book chapters end-to-end if the request is about one section.

If a session needs to violate this rule, name what it's reading and why. Default = stay narrow.

## Session closure protocol

Trigger phrases (any language): "סגירת צט", "בוא נסגור", "סיימנו", "נסיים כאן", "close chat", "wrap up", "we're done", "that's it for now."

When triggered, do all of this before ending:

1. **Save any pending work.** If there's an in-progress draft, save it now.
2. **Update `PROJECT_STATE.md`**:
   - Add what we completed this session to the "Completed" section.
   - Update "Active priorities" if anything shifted.
   - Update "Next session" with the next concrete action the user should take — include the exact opening phrase they can use (e.g., "Next time, say 'let's produce the inflation reel' to continue.").
3. **Update any rolling files** relevant to this session (Content Calendar status, Topic Pipeline produced flags, Weekly Review notes, etc.).
4. **Provide the commit message** for all changes made this session. Format described below.
5. **One-paragraph session summary** for the user — what we did, what's next, what they should do between sessions.

End state: the user can close the chat, push to GitHub, and come back to a fresh chat knowing exactly where we are and what to say next.

## Commit message rule

Any time a session makes file changes (create, edit, delete), provide a commit message at the end.

Format:
- Single line, imperative mood, under 72 characters.
- Prefix with scope in brackets when useful.
- If more context helps, add 2–4 body lines after a blank line.

Examples:
- `[content] Add REEL-001 inflation package`
- `[book] Editorial pass — chapters 1–5 typos fixed`
- `[strategy] Brand Bible + Hook Library v1`
- `[ops] Update agent routing with session closure protocol`

Give the user the exact text to paste into GitHub Desktop's commit field. No backticks, no formatting — plain text they can copy.

If multiple unrelated changes happened, offer multiple commits instead of one giant commit.

## The roster

- **01 - Content Strategist** — picks topics, plans week, owns Brand Bible.
- **02 - Reel Producer** — produces one Reel package per session (shoot sheet + meta).
- **03 - Book Publisher** — owns Tom's First Million end to end.
- **04 - Course Architect** — paused. Revisit after content engine converts.
- **05 - Funnel Builder** — bio, links, landing pages, CTAs, email.
- **06 - Analytics** — weekly numbers review, feeds Content Strategist.
- **07 - Stories** — produces 3–5 Stories per week. Repairs the funnel leak between Reels.
