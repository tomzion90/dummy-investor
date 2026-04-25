# Project State

**Last updated:** 2026-04-25
**Updated by:** Content Strategist (Brand Bible v1.1 + Hook Library v1.1 — English-only + Anti-Pattern Catalog)

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

1. **Produce first Reel under the new system** — Topic 2.1 Inflation, chart-as-hook cover (Style C), per the recommended rotation in `Topic Pipeline.md`. This is the first real test of Brand Bible + Hook Library. Agent: Reel Producer.
2. **Rebuild bio + CTA** — 0 link taps means traffic has nowhere to go. One link, benefit-driven bio, single explicit verbal CTA on every Reel. Agent: Funnel Builder.
3. **Book rescue** — Full editorial pass, redesign without background image, reflow to KDP trim, new listing copy, cover brief. Agent: Book Publisher.
4. **Weekly metrics review** — Every Sunday: Analytics agent reviews last 7 days, updates this file, feeds Content Strategist.
5. **Course polish (paused)** — Revisit in 4–6 weeks once content is growing.

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

**Brand foundations are set. Time to use them.**

**What to say to start:** in a fresh chat, type **"let's make the inflation reel"** (or just "let's make a reel" — I'll route to Topic 2.1 by default).

**What I will do:** route to the Reel Producer agent. Read Brand Bible + Hook Library + Topic Pipeline. Produce the full package for Topic 2.1 — Inflation: chart-as-hook cover (Style C), spoken hook, full script in Hebrew, on-screen text, CTA, file structure.

**Why this Reel first:** It's the first test of the new cover/hook system. Inflation is foundational (Pillar 2 — Mechanics), the chart-as-hook style is our most defensible against the old panic-cover habit, and the math is unarguable. If this Reel doesn't move the needle vs the last 20, the system needs revising — not the topic.

**Alternative next session if you want to fix the funnel first:** type **"let's fix the bio"** to route to the Funnel Builder. We have 0 link taps right now — the case for fixing the bio before producing more Reels is real. Either order works; pick based on energy.
