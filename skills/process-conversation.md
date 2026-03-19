---
last_accessed: YYYY-MM-DD
access_count: 0
created: YYYY-MM-DD
---

# Skill: Process conversation

## When to use

Triggered by the user via the `/reflect` command, or at the end of a work session.

## Procedure

### 1. Review the conversation

Read the current or most recent conversation. Identify:
- Decisions and their reasoning
- Tasks mentioned or captured
- Ideas discussed
- Meeting context or situational notes
- Lessons learned or patterns discovered
- Open threads (discussed but unresolved)

### 2. Update today's log

Open `memory/logs/YYYY-MM-DD.md` (today's date). If it exists, append new content
under the existing sections (avoid duplicating information already logged earlier
in the day). If it doesn't exist, create it with this structure:

```markdown
---
date: YYYY-MM-DD
last_updated: YYYY-MM-DDTHH:MM
---

# Log — YYYY-MM-DD

## Decisions
- [Decision and reasoning, with enough context for future reference]

## Tasks captured
- [What was captured and where it was filed]

## Ideas
- [Ideas discussed, whether filed or not]

## Context
- [Meetings, conversations with colleagues, situational context]

## Lessons
- [Patterns discovered, errors and fixes, things learned]

## Open threads
- [Discussed but unresolved — to pick up later]
```

Always update the `last_updated` timestamp in the frontmatter.

### 3. Verify captures

Check that everything actionable from the conversation has been properly captured:
- Tasks → `board/BOARD.md` (Inbox or appropriate section)
- Concrete improvement ideas / tech debt → `board/BOARD.md` Parked
- Unformed ideas / project concepts / draft proposals → `brain/ideas/`
- Decisions → `brain/projects/` or `brain/concepts/`
- Lessons → `brain/concepts/`
- Requests → `brain/requests/`

If anything was missed, capture it now.

### 4. Git commit

```bash
git add -A && git commit -m "reflect: YYYY-MM-DD" 2>/dev/null || true
```

## Quality criteria

- **Be specific.** "Discussed CI/CD" is useless. "Decided to migrate from Jenkins to
  Tekton because of X" is useful.
- **Focus on reasoning.** Decisions and their "why" are the most valuable content.
  Activity tracking is handled by external tools.
- **Don't inflate.** If the conversation was trivial, the log can be minimal.
- **Think of future you.** The log is for someone without today's context who needs
  to understand when and why something was decided.
- **Append, don't overwrite.** If the log already has content from an earlier
  processing pass, add new information without duplicating.
