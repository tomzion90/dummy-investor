# Editor notification template

Locked 2026-04-25. Used by Reel Producer (Agent 02) and Stories agent (Agent 07) after every Drive upload, in addition to the GitHub push email automation.

The Gmail MCP can only **draft** emails, not send them. Tom sends from his inbox after reviewing the draft.

## Recipients (TO)

- `tomezion@gmail.com`
- `Yuvalvul60@gmail.com`

(Same recipients as the GitHub push automation.)

## Subject lines

**For Reels:**
```
Reel "[Topic Name]" uploaded to Drive
```
Examples:
- `Reel "Inflation — what one dollar buys now" uploaded to Drive`
- `Reel "Ronald Read — the $8M janitor" uploaded to Drive`

**For Stories:**
```
Story uploaded to Drive
```
(Stories are short — no name needed in the subject.)

## Body — Reel

```
Hi Yuval,

A new Reel is ready to record.

Title: [Topic Name]
Length: 38–42 seconds
Format: [A — Chart-led / B — Demo-led / C — Story-led]
Folder: REELS

Doc link: [Google Doc URL from the Drive upload]

Everything you need (cover spec, script with timing, on-screen captions, B-roll, sound, export) is in the doc, top to bottom.

Let me know if anything is unclear before you start.

— Tom
```

## Body — Story

```
Hi Yuval,

A new Story is ready.

Category: [Recap / Process / Question / Brand-line]
Tied to: [REEL-### or "standalone"]
Folder: STORIES

Doc link: [Google Doc URL from the Drive upload]

— Tom
```

## Rules

- Keep the body short. Visual + link does the heavy lifting.
- Subject must contain the word "Reel" or "Story" so the inbox is searchable.
- Always link to the Google Doc, not the folder.
- Don't paste the full script in the email — that's what the Doc is for.
- The agent that uploads the file is also the agent that drafts the email. Both happen in the same session, after user approval.

## When to draft (workflow position)

```
1. Agent drafts the Reel/Story file locally
2. User approves
3. Agent uploads to Drive (REELS or STORIES) as native Google Doc
4. Agent creates Gmail draft using the template above
5. Tom opens Gmail Drafts, reviews, sends to the editor
6. Tom commits + pushes to GitHub (triggers the existing push-email automation as backup)
```

Steps 4 and 6 are both notifications. Step 4 is human-readable for the editor. Step 6 is for project audit trail.
