# Trello automation (Make.com bridge)

Started 2026-04-26. **LIVE.** Every approved Reel POSTs to a Make webhook, which auto-creates a card in Trello → board "Trading Dummy" → list "Scripting".

Stack: Make.com (free tier) bridges between us and Trello. We don't connect Trello directly because there's no native Trello MCP; Make.com is the cheapest, simplest bridge.

## Operational state (2026-04-26)

- **Make.com account:** `yutomshazion@gmail.com`. Free tier (1,000 ops/month, 2 active scenarios). At 3 Reels/week our usage is ~26 ops/month — plenty of headroom.
- **Trello connection in Make:** named `Dummy Investor Trello`. OAuth complete.
- **Scenario:** named `Integration Trello`. Two modules: Custom Webhook → Trello "Create a Card". **Toggle: ON** (auto-fires on every webhook hit, no manual Run once needed).
- **Webhook:** `Dummy Investor — new Reel`. URL: `https://hook.eu1.make.com/ucyad4tz71rk8eyhri8fwwrg8ne4d8i5`. Field structure captured — Make recognizes all 7 contract fields.
- **Trello "Create a Card" module:** Board = Trading Dummy, List = Scripting, Name + Description mapped per "Trello card content" below. Default Label `695d631472391c817ad91586` and default Member `68fd9d54a39e8aa6d95dd7c4` auto-applied to every card (intentional — Tom owns + a "Reel" label).
- **Cowork allowlist:** `*.make.com` whitelisted, verified working from the sandbox.

## End-to-end verified

`TEST-001 — End-to-end Trello automation test` was POSTed via curl from the Cowork sandbox at 2026-04-26 09:41 UTC. Webhook returned `HTTP/2 200 — Accepted`. Card landed in board Trading Dummy → list Scripting within seconds. Card archived after verification.

## How to fire a card from a Reel session

After a Reel script is approved + uploaded to Drive + Gmail draft created (steps 1–4 of the Reel Producer approval-then-save flow), POST the contract payload to the webhook:

```bash
curl -X POST 'https://hook.eu1.make.com/ucyad4tz71rk8eyhri8fwwrg8ne4d8i5' \
  -H 'Content-Type: application/json' \
  -d '{
    "reel_id": "REEL-001",
    "title": "<topic title>",
    "format": "Story-led",
    "topic": "<one-word topic>",
    "spoken_hook": "<first sentence of the script>",
    "drive_link": "<Google Doc URL>",
    "editor_draft_link": "<Gmail draft URL>"
  }'
```

Expect `HTTP/2 200 — Accepted`. Card appears in Scripting within 2–3 seconds.

## Open question (TBD with Tom)

Should the Stories agent (07) also fire Trello cards? Same webhook + new payload contract, or a separate webhook + scenario, or skip Trello for Stories entirely. Decide before the first Stories week.

## Payload contract (what to POST to the webhook)

```json
{
  "reel_id": "REEL-001",
  "title": "Inflation — the silent tax",
  "format": "Story-led",
  "topic": "Inflation",
  "spoken_hook": "In 1971, a man named Ronald Read...",
  "drive_link": "https://docs.google.com/document/d/...",
  "editor_draft_link": "https://mail.google.com/mail/u/0/#drafts/..."
}
```

`format` is one of `Chart-led` / `Demo-led` / `Story-led` (Brand Bible §7).

## Trello card content (how to map webhook fields)

**Card Name:**
```
{{reel_id}} — {{title}}
```
Renders as: `REEL-001 — Inflation — the silent tax`

**Card Description:**
```
Format: {{format}}
Topic: {{topic}}

Spoken hook:
{{spoken_hook}}

Drive doc: {{drive_link}}
Editor draft: {{editor_draft_link}}
```

Drop into list: **Scripting** (board: Trading Dummy).

## Per-Reel runtime cost

~2 Make ops per fire (1 webhook receive + 1 Trello create). At 3 Reels/week → ~26 ops/month. Free tier ceiling: 1,000 ops/month.

## Why not Trello directly

No native Trello MCP in the Cowork registry as of 2026-04-26. Make.com is the cheapest free bridge. monday.com has a native MCP but costs $9–12/user/month — not worth it for the marginal convenience.
