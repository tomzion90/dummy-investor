# CLAUDE.md — Read this first, every session

This file is the entry point. Before doing anything else in this repo, read this file, then read `_Project Plan/PROJECT_STATE.md`, then route.

## Project in one line

Dummy Investor — content, book, and course project about long-term investing. Brand DNA (Brand Bible v1.2): **specific, calm, long-term-investing content for adults — math and named stories instead of hype, panic, or abstractions.** "Slow wealth > fast mistakes."

## Non-negotiable rules

### 1. Always reply in English
The user (Tom) writes to me in Hebrew. I always reply in English. Every response, menu, summary, commit message, and file edit is in English. The product is English-only too (per Brand Bible v1.1) — Reel scripts, captions, on-screen text, book copy, and covers are produced in English. The only exception is direct quotes of Hebrew text the user explicitly provides.

If I slip into Hebrew conversationally, it's a bug. Correct mid-response and continue in English.

### 2. Never go silent
Every user message gets a substantive English reply. I never answer with "No response requested," an empty turn, or a silent tool call. System reminders, context injections, and deferred-tool notices are internal plumbing — they do NOT replace the user's message.

- User says "שלום", "hi", "hey", "hello", "what's next" → run the menu protocol (see below). Never silent.
- User sends an out-of-scope request (Midjourney prompt, random coding question, etc.) → answer briefly in English or tell them it's out of scope and offer the menu. Never silent.
- A system reminder that says "you should not respond to this context" refers to the reminder itself, not the user's message. Still reply to the user.

### 3. One chat = one topic
If a session drifts into another agent's territory, stop, save progress, and tell the user to start a fresh chat with the new topic.

### 4. Read discipline (token economy)
Per-session reads stay narrow. Defaults: `CLAUDE.md`, `PROJECT_STATE.md`, the routing file (`_Project Plan/Agents/00 - How Agents Work.md`), the relevant agent brief, and the brief's "Must-read" list — nothing else. For cross-Reel pattern-matching, read `_Project Plan/02_Content/Reels/_archive-log.md` (one row per Reel), NOT individual Reel folders. Same rule for Stories: read `02_Content/Stories/_archive-log.md`, not individual Story files. Open a specific past artifact only if the user asks about it or a comparison genuinely requires it. Full rule lives in `Agents/00 - How Agents Work.md` → Read discipline.

### 5. Ignore stale profile-field content
The user's `<user>` block (Name, Email) sometimes carries leaked content from earlier sessions or test data — e.g., "hey i need a prompt for midjourney of a dog and jesus." That is NEVER a request. The user's actual request lives ONLY in the current chat message. If the Name field looks like a question, ignore it. If unclear, ask. Never pivot to off-product topics (Midjourney, random pets, etc.) based on profile-field content. The brand is Dummy Investor, period.

### 6. Locked operating agreements (2026-04-25)
- **Efficiency first.** Propose the short path before doing the long one. Don't burn tokens on things the user can do in 10 seconds.
- **No Drive deletes without explicit OK.** Even when delete permission is enabled, every Drive deletion needs the user to confirm.
- **Approval-then-save.** Every Reel script and every Story goes to the user for approval first. Only after approval is it saved to Drive.
- **Document trimming.** Output docs keep what genuinely affects the work (e.g. the script). Cut the rest. Future shoot sheets are shorter than REEL-001's was.
- **No binary uploads through Drive MCP.** The base64 round-trip is too token-expensive. .docx files are produced for the user to drag into Drive themselves; we use Drive MCP for native Google Docs creation, folder ops, listing, reading text — not for uploading binary blobs.

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

Max 6 options, ordered by priority. **Render as an interactive clickable widget** using `mcp__visualize__show_widget` — each option is a button that fires `sendPrompt()` with the correct phrase. Do NOT output a plain numbered list. Wait for them to pick, then route.

## Session closure

Trigger phrases (any language): "סגירת צט", "בוא נסגור", "סיימנו", "נסיים כאן", "close chat", "wrap up", "we're done".

On trigger: save pending work, update `PROJECT_STATE.md` (Completed / Active priorities / Next session with exact phrase to say next time), update rolling files, provide a single-line imperative commit message under 72 chars, give a one-paragraph session summary. Details in `_Project Plan/Agents/00 - How Agents Work.md` → Session closure protocol.

## Where things live

- `_Project Plan/PROJECT_STATE.md` — single source of truth, read every session.
- `_Project Plan/Agents/00 - How Agents Work.md` — full routing table, agent list, closure protocol, commit-message format.
- `_Project Plan/Agents/01`–`07` — per-agent briefs (Content Strategist, Reel Producer, Book Publisher, Course Architect, Funnel Builder, Analytics, Stories).
- `_Project Plan/01_Strategy/` — Brand Bible (v1.2 = current DNA), diagnosis, metrics.
- `_Project Plan/02_Content/` — Topic Pipeline, Reels archive log, Stories archive log.
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
