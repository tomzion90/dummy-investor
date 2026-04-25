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

(empty — first Reel under DNA v2 will be added when Reel Producer runs next)

## How to add a new row

When a Reel is shipped:
1. Append one row at the bottom. Don't reorder.
2. Fill `Shipped` immediately. `Posted` and view columns get filled later, by Tom or by the Analytics agent during the weekly review.
3. After the first weekly review that includes the Reel, write the one-line takeaway in `Notes` (e.g., "Best 7d views to date — chart cover validated."). Keep it terse.
