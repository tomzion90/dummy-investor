# Dummy Investor — Project Operating System

This folder is the brain of the project. Every decision, every deliverable, every agent role lives here. It's designed so any new chat can get up to speed in under 30 seconds.

## How to start a chat

Just say **"שלום"** or **"hi"** or **"hey"**. That's it.

I will:
1. Read `PROJECT_STATE.md` to see where we left off.
2. Show you the active options as a short menu.
3. You pick (or tell me something else you want to do).
4. I read the right agent brief + files, do the work, save it, and update `PROJECT_STATE.md`.

You never paste prompts. You never specify files. You just talk.

## The golden rule

One chat, one topic. If mid-chat you realize we've drifted into a different agent's territory, tell me and I'll stop, save progress, and you can start a fresh chat. This keeps my context clean.

## File index

- `README.md` — this file.
- `PROJECT_STATE.md` — single source of truth for where we are right now. I read this first, every time.
- `01_Strategy/` — brand voice, diagnosis, metrics.
- `02_Content/` — Reels, hook library, content calendar.
- `03_Book Publishing/` — book fixes, KDP prep, listing copy.
- `04_Course/` — syllabus, lessons, scripts (currently paused).
- `05_Funnel & Sales/` — bio, landing pages, email, CTAs.
- `06_Weekly Reviews/` — one file per week, written by Analytics agent.
- `Agents/` — one file per agent role. You don't need to read these; I do.

## How a session ends

Before the chat wraps, I always:
1. Save the output to the right folder.
2. Update `PROJECT_STATE.md` with what was done and what the next session should be.
3. Tell you in one sentence what to say next time to continue.

## Git note

Safe to commit. No secrets, no keys. Add `.DS_Store` to `.gitignore` if you init a repo here.
