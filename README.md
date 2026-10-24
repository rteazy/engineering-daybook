# Engineering Daybook

A structured and machine-readable Markdown format for an [engineering daybook](https://www.oreilly.com/library/view/the-pragmatic-programmer/9780135956977/f_0041.xhtml).

## What's in a daybook

A daybook is one Markdown file per day:

```markdown
---
date: 2026-10-22
---

## Tasks

### auth-migration
- [x] fix token refresh race
  - unblocks Nov 3 cutover
- [/] write prod rollout plan
- [!] get prod DB credentials
  - waiting on infra

## Learning

- [/] "Designing Data-Intensive Applications" ch. 5

## Notes

Fixed the race with a Redis lock on session id.
```

## Daybook format

- Filename: `YYYY-MM-DD.md`, matching the `date` in the frontmatter.
- Frontmatter: `date: YYYY-MM-DD`.
- `## Tasks`: checklist grouped by `### project` headings. Each day, copy forward every task marked "yes" in [Task states](#task-states), keeping the text exactly the same.
  - Indented child lines under a task are notes about it.
- `## Learning`: checklist for personal learning. Uses the same task states and copy-forward rule as Tasks.
- `## Notes`: free-form notes not tied to a task.

## Task states

| Box   | Meaning         | Copied forward |
|-------|-----------------|----------------|
| `[ ]` | open            | yes            |
| `[/]` | worked on today | yes            |
| `[!]` | blocked         | yes            |
| `[x]` | done            | no             |
| `[-]` | dropped         | no             |

## User journeys

Because the format is consistent, an LLM can read your daybooks and answer questions about your work. Keep your daybooks in one folder, point an LLM (e.g. Claude Code) at it along with this README, and try prompts like these:

- **Starting your day:** "Create today's daybook, copying forward tasks from yesterday."
- **Preparing for a review:** "My manager asked what my main accomplishments were last quarter. Look at the work I completed in Q4 and summarize my main accomplishments."
- **Reflecting on growth:** "What new things did I learn in the last 3 months?"
- **Getting unstuck:** "What's been blocked the longest, and who am I waiting on?"

## Examples

See [example-daybook.md](example-daybook.md) for a full daybook.
