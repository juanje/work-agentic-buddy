---
last_accessed: YYYY-MM-DD
access_count: 0
created: YYYY-MM-DD
---

# Skill: Run standup

## When to use

Use when the user says "standup", "what's on my plate", "what did I do yesterday",
"what should I work on", "daily", or starts a session without a specific request.

## Procedure

### 1. Gather data

Run these in parallel to save time:
- Check recent logs in `memory/logs/` for yesterday's activity.
- Read `board/BOARD.md` — board state.
- If external tools are configured in AGENTS.md (e.g. issue tracker CLI, activity
  aggregators), use them to get what was done and what's pending.

If any tool is unavailable or fails, skip it and note it.

### 2. Present the standup

**What was done** (from logs and/or external tools):
- Summarize key activities grouped by project or theme.
- If data sources returned nothing or weren't available, say so honestly.

**Currently doing** (from board):
- Show the "Doing" section.

**Next up** (from board):
- Show the "Next Actions" queue.
- If Next Actions is empty or stale, suggest items from Inbox or Parked.
- Ask: "Does this look right, or should we adjust priorities?"

**Waiting/Blocked:**
- Show board "Waiting" items and how long each has been waiting (from `added` date).
- Items waiting >7 days: suggest escalation.

**Inbox check:**
- If there are untriaged items: "You have N items in Inbox to triage."

### 3. Update the board

If the user adjusts priorities or moves items, update `board/BOARD.md` accordingly.
