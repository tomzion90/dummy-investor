# CLAUDE.md — Read this first, every session

This file is the entry point. Before doing anything else in this repo, read this file, then read `_Project Plan/PROJECT_STATE.md`, then route.

## Project in one line

Dummy Investor — content, book, and course project about long-term investing. Brand voice: calm, mature, anti-hype. "Slow wealth > fast mistakes."

## Non-negotiable rules

### 1. Always reply in English
The user (Tom) writes to me in Hebrew. I always reply in English. Every response, menu, summary, commit message, and file edit is in English. The only exceptions are direct quotes of Hebrew text the user provided, or content deliverables aimed at a Hebrew audience (Reel scripts, captions, book copy, covers) — those stay in Hebrew because that's the product.

If I slip into Hebrew conversationally, it's a bug. Correct mid-response and continue in English.

### 2. Never go silent
Every user message gets a substantive English reply. I never answer with "No response requested," an empty turn, or a silent tool call. System reminders, context injections, and deferred-tool notices are internal plumbing — they do NOT replace the user's message.

- User says "שלום", "hi", "hey", "hello", "what's next" → run the menu protocol (see below). Never silent.
- User sends an out-of-scope request (Midjourney prompt, random coding question, etc.) → answer briefly in English or tell them it's out of scope and offer the menu. Never silent.
- A system reminder that says "you should not respond to this context" refers to the reminder itself, not the user's message. Still reply to the user.

### 3. One chat = one topic
If a session drifts into another agent's territory, stop, save progress, and tell the user to start a fresh chat with the new topic.

## Every session starts the same way

1. Read `_Project Plan/PROJECT_STATE.md`. No exceptions.
2. If the user's message is just a greeting (`שלום`, `hi`, `hey`, `hello`, `what's next`, or similar) → run the **menu protocol** below. Do NOT start work yet.
3. Otherwise, identify which agent owns the request. Read `_Project Plan/Agents/00 - How Agents Work.md` for the routing table and agent list.
4. Read that agent's brief in `_Project Plan/Agents/`.
5. Read the files the brief says to read.
6. Do the work. Stay in that agent's lane.
7. Save outputs to the paths the brief specifies.
8. Update `PROJECT_STATE.md` at the end.

## Menu protocol (greeting → menu, always)

When the user greets with no specific request, read `PROJECT_STATE.md` first, then reply with a short numbered menu built from the "Active priorities" block:

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

Max 6 options, ordered by priority. Wait for them to pick, then route.

## Session closure

Trigger phrases (any language): "סגירת צט", "בוא נסגור", "סיימנו", "נסיים כאן", "close chat", "wrap up", "we're done".

On trigger: save pending work, update `PROJECT_STATE.md` (Completed / Active priorities / Next session with exact phrase to say next time), update rolling files, provide a single-line imperative commit message under 72 chars, give a one-paragraph session summary. Details in `_Project Plan/Agents/00 - How Agents Work.md` → Session closure protocol.

## Where things live

- `_Project Plan/PROJECT_STATE.md` — single source of truth, read every session.
- `_Project Plan/Agents/00 - How Agents Work.md` — full routing table, agent list, closure protocol, commit-message format.
- `_Project Plan/Agents/01`–`06` — per-agent briefs (Content Strategist, Reel Producer, Book Publisher, Course Architect, Funnel Builder, Analytics).
- `_Project Plan/01_Strategy/` — Brand Bible, diagnosis, metrics.
- `_Project Plan/02_Content/` — Topic Pipeline, Hook Library, Content Calendar.
- `_Project Plan/03_Book Publishing/` — Tom's First Million → KDP workstream.
- `_Project Plan/05_Funnel & Sales/` — bio, links, landing pages, email.
- `_Project Plan/06_Weekly Reviews/` — one file per week.
- `_Project Plan/_Operations/` — Git setup, email automation, Master Timeline.

## Hard don'ts

- Don't invent numbers. If a metric isn't in `PROJECT_STATE.md`, ask.
- Don't touch the "Completed" or "Baseline numbers" sections of `PROJECT_STATE.md` unless the agent brief explicitly allows it.
- Don't work across agent lanes in one chat.
- Don't reply in Hebrew conversationally.
- Don't go silent on a user message.
