# Reels — Archive log

One row per shipped Reel. **This is the only file future sessions read when they need to pattern-match across the catalog.** Individual Reel folders are NOT read in normal sessions (see `Agents/00 - How Agents Work.md` → Read discipline).

If a session needs to dig into a specific past Reel (e.g., the user asks about it, or the Analytics agent needs to compare two performers), open that one folder explicitly — never the whole `Reels/` directory.

## Schema

| Column | Meaning |
|---|---|
| # | Reel number (REEL-###) |
| Topic | Topic ID + short name from Topic Pipeline |
| Pillar | 1–6 from Brand Bible §6 |
| Format | A (Chart-led) / B (Demo-led) / C (Story-led) — Brand Bible v1.2 §7 |
| Cover | A (Number) / B (Demo) / C (Chart) — Brand Bible v1.2 §11 |
| CTA | soft-brand / link / book / etc. |
| Shipped | Date the script package was completed |
| Posted | Date posted on IG (TBD until live) |
| 24h | Views at 24h |
| 7d | Views at 7d |
| 30d | Views at 30d |
| Notes | One-line takeaway after weekly review |

## Catalog

| # | Topic | Pillar | Format | Cover | CTA | Shipped | Posted | 24h | 7d | 30d | Notes |
|---|---|---|---|---|---|---|---|---|---|---|---|
| REEL-001 | 2.2 Compound interest — Anne Scheiber | 2 | C (Story-led) | A (Number) | soft-brand follow | 2026-04-29 (v3 FINAL) | TBD | — | — | — | First Reel under DNA v2. Shoot sheet rebuilt twice — final format mirrors Topic #12 production template (HOOK / MAIN SCRIPT / ENDING with stacked delivery lines, then EDITING with AVATAR/B-ROLL alternation incl. trigger lines + Envato searches + durations, then music, SFX, pinned comment, IG caption). This is now the locked production format for all future Reels. |
| REEL-002 | 4.10 Every crash since 1975, on one chart | 4 | A (Chart-led) | C (Chart) | soft-brand follow | 2026-05-07 | TBD | — | — | — | First Format A Reel. Chart opens the video (no face first frame). 5 labeled crashes (1973/1987/2000/2008/2020) + $65K/$1K recovery number. Drive doc: 11lD3raUvLWCLnYAGrb7KsMVZqU7Y0uI33i0VksBPy44 |

## How to add a new row

When a Reel is shipped:
1. Append one row at the bottom. Don't reorder.
2. Fill `Shipped` immediately. `Posted` and view columns get filled later, by Tom or by the Analytics agent during the weekly review.
3. After the first weekly review that includes the Reel, write the one-line takeaway in `Notes` (e.g., "Best 7d views to date — chart cover validated."). Keep it terse.
| REEL-003 | 1.1 The real cost of waiting 10 years | 1 | B (Demo-led) | B (Demo) | soft-brand follow | 2026-05-07 | TBD | — | — | — | Format B first use. Sara ($24K invested, 10yrs) beats Kevin ($72K invested, 30yrs) — $281K vs $244K at 65. Counterintuitive hook. Drive doc: 1n9HcGl2sU99RamRRR5Hnsn4d78aDXJ6s5QnTFqIP-bU |
| REEL-004 | 5.1 DCA in 60 seconds | 5 | A (Chart-led) | C (Chart) | soft-brand follow | 2026-05-07 | TBD | — | — | — | Format A, Pillar 5. $200/month, 30yrs, 10% avg → $452,000 vs $72,000 invested. Chart with monthly buy markers. Drive doc: 1H4-NUFpdSVl2K3f2UryPjqiX9PNRZLO9q-BkJjxjpkA |
