# How Agents Work (Routing Guide — I read this)

This file tells me (the AI) how to route a user request to the right agent and files. The user does not need to read this.

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
| "plan next week", "pick topics", "what should I post", "brand voice", "pillars" | Content Strategist (`01`) | Brand Bible, Hook Library, latest weekly review |
| "make a reel", "write a script", "produce content about X", "new video" | Reel Producer (`02`) | Brand Bible, Hook Library, Content Calendar, current bio CTA, last 2 reel folders |
| "book", "Tom's First Million", "KDP", "cover brief", "book listing" | Book Publisher (`03`) | Brand Bible, existing book files, prior book passes |
| "course", "syllabus", "lesson" | Course Architect (`04`) | (Currently paused — confirm with user before unpausing) |
| "bio", "link in bio", "landing page", "funnel", "email", "CTA" | Funnel Builder (`05`) | Brand Bible, Content Diagnosis, prior funnel files |
| "weekly numbers", "review this week", "what worked", "what's performing" | Analytics (`06`) | Most recent weekly review, baseline in PROJECT_STATE |
| Ambiguous / "what's next" / "hey" | Project Lead (me, default) | Just PROJECT_STATE.md — then ask user to pick |

## When the user is ambiguous

Don't guess. Read PROJECT_STATE.md, then offer them the 2–3 most logical next sessions based on the active priorities. Let them pick.

## Agent rules that apply to all

- Never work outside your scope. If the user's request crosses into another agent's territory mid-session, stop, save what's done, and tell them to start a fresh chat with the new topic.
- Never invent numbers. If a metric is needed and not in PROJECT_STATE.md, ask.
- Always save outputs to the path specified in the agent brief.
- Always update PROJECT_STATE.md at the end.
- Never touch the "Completed" or "Baseline numbers" sections of PROJECT_STATE.md unless the agent brief explicitly allows it.

## The roster

- **01 - Content Strategist** — picks topics, plans week, owns Brand Bible and Hook Library.
- **02 - Reel Producer** — produces one full Reel package per session.
- **03 - Book Publisher** — owns Tom's First Million end to end.
- **04 - Course Architect** — paused. Revisit after content engine converts.
- **05 - Funnel Builder** — bio, links, landing pages, CTAs, email.
- **06 - Analytics** — weekly numbers review, feeds Content Strategist.
