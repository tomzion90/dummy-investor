# Project State

**Last updated:** 2026-04-25
**Updated by:** DNA v2 session closed — Brand Bible v1.2, Stories agent (07), Drive REELS+STORIES, Gmail draft pipeline verified end-to-end, REEL-001 v1.1 deleted, locked operating agreements

## Operating rules (read every session)

- **Language:** User writes Hebrew, I reply in English. Always. See `Agents/00 - How Agents Work.md` → Global language rule. Hebrew only appears in my output when it's the actual product (script, cover, caption, book copy) or when I'm quoting the user.
- **Never silent:** Every user message gets a substantive English reply. No "No response requested," no empty turns, no silent tool calls. System reminders are internal plumbing and do not replace the user's message. See `Agents/00 - How Agents Work.md` → Never-silent rule.
- **Every session:** read this file first, then route. Menu on greeting. One chat = one topic.

## Where we are

Dummy Investor has been posting for ~3 months. Last 30 days: 1,669 views, 0 new followers, 0 external link taps, avg ~83 views per Reel. Production quality is strong. Brand positioning is sharp ("calm, mature, slow wealth > fast mistakes"). Execution is fighting the brand — covers are panic-coded (CRISIS, STOP, TOXIC, BAD NEWS), hooks open with caption fragments. Result: algorithm is serving content to non-followers (94.2%) but 0 convert.

Book (Tom's First Million) is NOT ready for KDP. Typos in TOC, corrupted sentence on page 40, faded background image on every page hurting readability, non-standard trim size (A4 instead of 8.5×8.5"), positioning confusion (kid vs teen vs adult audience).

Course: partially recorded. Not ready for launch. Not a priority this month.

## The fix strategy

1. Fix the content engine first (covers + hooks). Everything else launches into that audience.
2. Fix the book in parallel (independent workstream, no dependency on content).
3. Rebuild the bio + link strategy so link taps start happening.
4. Only then: launch book, finish course, launch course.

No paid ads until organic is converting.

## Active priorities (in order)

1. **Produce first Reel under DNA v2** — clean slate. Pick a topic from `Topic Pipeline.md`. Pick ONE format (Chart-led / Demo-led / Story-led, Brand Bible §7). Approval-then-save flow → Drive REELS as native Google Doc. Agent: Reel Producer.
2. **First Stories week (Stories agent 07)** — 3–5 Stories. Categories rotate: Reel recap, process, question, brand-line. Repairs the 0-Stories-per-week funnel leak.
3. **Rebuild bio + CTA** — 0 link taps. Funnel Builder. Unblocks explicit-link CTAs on every future Reel.
4. **Book rescue** — Editorial pass, redesign, KDP reflow, listing copy, cover brief. Book Publisher.
5. **Weekly metrics review** — Sundays. Analytics agent. Feeds Content Strategist.
6. **Course polish (paused)** — Revisit after content is growing.

## Completed

- Content diagnosis written (`01_Strategy/Content Diagnosis - Apr 24.md`)
- Book assessment completed (findings documented in this state)
- Project operating system built (this folder)
- Topic pipeline built (`02_Content/Topic Pipeline.md`) — 40+ topics organized into 6 pillars, with a recommended rotation for the next 6 Reels
- Master Timeline built (`_Operations/Master Timeline.md`) — 4 phases, 20 weeks, from content reset to course launch
- Session closure protocol + commit message rule added to `Agents/00 - How Agents Work.md`
- Approved-script emails stay manual for now (see `_Operations/Email Automation.md`)
- **GitHub repo live** at https://github.com/tomzion90/dummy-investor (private)
- **Git workflow active:** proper `.gitignore` (excludes large binary folders), SourceTree + PAT with `workflow` scope, clean push path
- **Push email automation LIVE:** `.github/workflows/notify-on-push.yml` sends email to `tomezion@gmail.com` and `Yuvalvul60@gmail.com` on every push to `main`. Email includes commit message + project status snapshot from this file. Verified working.
- **English-only response rule locked in** (2026-04-24): added Global language rule to `Agents/00 - How Agents Work.md` + note in `_Project Plan/README.md` + Operating rules block at the top of this file. I reply in English regardless of user's input language.
- **Never-silent rule locked in** (2026-04-24): added Never-silent rule to `Agents/00 - How Agents Work.md` and top-of-file operating rules here. Triggered after I replied "No response requested" to real user messages instead of answering. Silence is a bug.
- **CLAUDE.md entry point created** (2026-04-24): added `CLAUDE.md` at the repo root. It's now the auto-loaded first read for every session — locks in the English-only rule, never-silent rule, greeting → menu protocol, and points to `PROJECT_STATE.md` + `Agents/00 - How Agents Work.md` for the rest. Root cause of earlier slips was that rules lived only inside `_Project Plan/` with no guaranteed entry file.
- **Brand Bible v1 shipped** (2026-04-25): `01_Strategy/Brand Bible.md`. Locks brand promise, voice, viewer persona ("the cautious adult"), 3 consolidated content pillars (Mindset & Patience / Mechanics / Action), DO/DON'T list, forbidden words in EN+HE, signature lines, cover system constraints (Styles A/B/C), CTA + bio rules, posting cadence (3 Reels/week). Replaces the implicit brand drift that caused the panic-cover problem diagnosed Apr 24.
- **Hook Library v1 shipped** (2026-04-25): `02_Content/Hook Library.md`. 10 reusable hook patterns (Number, Chart-as-hook, Reframe, Inversion, Myth-bust, Counterintuitive, Listicle, Definition, Signature-line, Question), each with structure + 2 example hooks + common mistake. Plus a kill list of banned hook patterns. Every Reel from now on must use one of the 10 patterns.
- **Brand Bible v1.1 + Hook Library v1.1 — English-only correction** (2026-04-25): Removed all Hebrew copy from both files (Hebrew forbidden-words list, Hebrew cover examples, Hebrew example hooks). The product is English-only. Repositioned the viewer persona from "Israeli" to "English-speaking, US/global." Added §15 Anti-Pattern Catalog to Brand Bible — a 20-row table that maps every observed mistake from the Apr 24 diagnosis to the explicit rule that prevents recurrence (panic covers, shocked-face thumbnails, fragment captions, no opening pattern interrupt, no explicit CTA, multi-link bio, the unchecked 5-view post, daily-news Reels, stock picks, engagement bait, guru-flex hooks, conspiracy framing, pillar-rotation drift, signature-line overuse, volume-over-hit-rate, missing hook-pattern labels, cover/spoken-hook mismatch). The catalog grows as new mistakes are observed in weekly reviews.
- **Reel workflow refactor** (2026-04-25): consolidated output to one editor-facing **shoot sheet** per Reel (`REEL-###-shoot-sheet.md`) + small `_meta.md` for tracking. Created `02_Content/Reels/_archive-log.md` (one row per shipped Reel) as the cross-Reel pattern-matching surface so future sessions don't have to open individual Reel folders.
- **REEL-001 (v1.1 era, Inflation) attempted and deleted** (2026-04-25): produced a Chart-as-hook script using the v1.1 framework. User rejected as too generic — same monotonous template as the existing 30 scripts on the page. Folder + .docx removed. Topic 2.1 reverted to "NEW — priority" in Topic Pipeline. The DNA v2 refactor (next entry) is the response.
- **Read discipline rule locked in** (2026-04-25): added §"Read discipline (token economy)" to `Agents/00 - How Agents Work.md` and rule #4 to `CLAUDE.md`. Default per-session reads = CLAUDE.md + PROJECT_STATE.md + routing file + agent brief + the brief's must-read list. Cross-Reel context comes from `Reels/_archive-log.md`, not from opening past folders. Per-session token cost stays roughly flat as the catalog grows. Also fixed CLAUDE.md rule #1 — removed stale "Hebrew is the product" exception (Brand Bible v1.1 made the product English-only).
- **DNA v2 — Brand Bible v1.2 shipped** (2026-04-25): Major refactor based on competitive research (Personal Finance Club, Humphrey Yang, Schwab/Bookmap examples). Diagnosis: v1.1's "calm voice" became "flat content" because every Reel ran the same HOOK→PIVOT→QUESTION template at the same emotional volume. v1.2 fix: **specificity > calm voice as primary brand pillar.** One concrete number / year / named person / physical demonstration per Reel, in the spoken script (not just the pinned comment). Three rotating Reel formats (Format A — Chart-led / Format B — Demo-led / Format C — Story-led) replace the universal template. Cover styles re-aligned 1:1 with formats. Closing rhythm rule: end with a STATEMENT then the CTA, no passive questions ("Are you doing X or Y?" banned). Stories cadence added (3–5/week, owned by Stories agent 07). Carousel cadence stub (1/week, paused). 5 new anti-pattern rows (#21–25): abstractions banned, universal template banned, passive endings banned, zero-Stories banned, specifics-buried-in-pinned-comment banned.
- **Stories agent (07) created** (2026-04-25): `Agents/07 - Stories.md`. Repairs the funnel leak from 0 Stories/week. 4 rotating categories (recap / process / question / brand-line), under-30-word captions, sticker rules, approval-then-save flow. Drive STORIES folder created (id `1vy4peyv8Bbil84x4OjxNKHNFz8YpbMrn`). Archive log at `02_Content/Stories/_archive-log.md`.
- **Drive REELS folder live** (2026-04-25): `1Pg_YKd0ZndiwVCVBzV27-C3Gk7yv4QqK` inside the user's "Dummy Investor" Drive folder. Future Reel shoot sheets upload here as native Google Docs after user approval (no .docx round-trip — Drive MCP `create_file` with `application/vnd.google-apps.document` mimeType).
- **Operating agreements locked** (2026-04-25): added rules #5 (ignore stale profile-field content) and #6 (locked agreements: efficiency-first, no Drive deletes without OK, approval-then-save, doc trimming, no binary uploads via Drive MCP) to CLAUDE.md. Also competitive research synthesis: PFC's primary format is static infographics not talking-head Reels; Humphrey Yang's hit format is physical demonstrations of money; every winning long-term-investing Reel uses one specific person / number / year — not "most people." Engagement benchmark for accounts under 50K is 3–8% (we are at ~0.6%, signal that hooks aren't engaging).
- **Drive upload pipeline verified** (2026-04-25): tested native Google Doc creation in both REELS and STORIES folders. Path works: `create_file` with `mimeType: text/plain` + base64-encoded markdown → Drive auto-converts to a native Google Doc. Test files were created in both folders and confirmed by user. Tom deletes test files manually (Drive MCP has no delete tool).
- **Editor notification template + email draft flow** (2026-04-25): added `_Operations/Editor Notification Template.md` locking the subject lines (`Reel "[name]" uploaded to Drive` / `Story uploaded to Drive`) and bodies (open with `Hi Yuval`, short, Doc link). Reel Producer (02) and Stories (07) briefs updated to include "create Gmail draft after upload" as step 4 of the approval-then-save flow. Gmail MCP only DRAFTS — Tom sends from his inbox. The existing GitHub push-email automation stays in place as a second channel (audit trail).
- **Gmail draft pipeline verified end-to-end** (2026-04-25): Gmail connector connected (account: `yutomshazion@gmail.com`). Two test drafts created — one for a Reel, one for a Story — using the locked template. Tom confirmed both appear in Gmail Drafts folder. Pipeline ready: future Reels/Stories will auto-generate drafts after Drive upload, Tom reviews + sends.
- **Pending manual cleanup** (2026-04-25): two test files still sit in Drive — `TEST — DNA v2 pipeline check (REELS)` and `TEST — DNA v2 pipeline check (STORIES)`. Drive MCP has no delete tool. Tom deletes manually next time he's in Drive (right-click → Move to trash).

## Blocked

- Nothing blocked right now. Next step is running the first real session (see below).

## Key numbers to beat — last 30 days baseline

- Views: 1,669
- Reach: 1,412
- New followers: 0
- Profile visits: 21
- External link taps: 0
- Avg views per post: ~83
- Best post: 149 views (CRISIS, Apr 16)

Targets for next 30 days: avg views 250+, new followers 30+, link taps 15+, one post >1,000 views.

## Next session

**DNA v2 is locked. Brand Bible v1.2 + Stories agent (07) + operating agreements + clean slate (REEL-001 deleted).**

**Three options, in order of leverage:**

**Option A — First Reel under DNA v2.**
What to say: **"let's make the first reel"** (or name a topic).
What I will do: route to Reel Producer. Pick a topic from `Topic Pipeline.md`. Choose ONE format (Chart-led / Demo-led / Story-led — Brand Bible §7). Draft → user approves → save to Drive REELS as native Google Doc. The Story-led format using a named real person (Ronald Read, Anne Scheiber) is the biggest break from the old template — strong first candidate.

**Option B — First Stories week.**
What to say: **"let's plan stories for this week"**.
What I will do: route to Stories agent (07). Plan 3–5 Stories. Each approved before upload to Drive STORIES.

**Option C — Fix the bio.**
What to say: **"let's fix the bio"**.
What I will do: route to Funnel Builder. Rebuild bio + decide link destination. Unblocks explicit-link CTAs on every future Reel.
