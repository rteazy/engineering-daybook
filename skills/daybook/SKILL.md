---
name: daybook
description: Use when the user wants to create, update, or ask questions about their engineering daybooks (one Markdown file per day named YYYY-MM-DD.md). Triggers include "start my day", "create today's daybook", "what did I accomplish", "what did I learn", and "what's blocked".
---

# Engineering Daybook

## Finding daybooks

Daybooks live in one folder. Use the current working directory unless the user names another. If no `YYYY-MM-DD.md` files are there, ask the user where their daybooks are.

## Daybook format

- Filename: `YYYY-MM-DD.md`, matching the `date` in the frontmatter.
- Frontmatter: `date: YYYY-MM-DD`.
- `## Tasks`: checklist grouped by `### project` headings.
  - Indented child lines under a task are notes about it.
- `## Learning`: checklist for personal learning. Uses the same task states as Tasks.
- `## Notes`: free-form notes not tied to a task.

See [references/example-daybook.md](references/example-daybook.md) for a full daybook.

## Task states

| Box   | Meaning         | Copied forward |
|-------|-----------------|----------------|
| `[ ]` | open            | yes            |
| `[/]` | worked on today | yes, as `[ ]`  |
| `[!]` | blocked         | yes            |
| `[x]` | done            | no             |
| `[-]` | dropped         | no             |

## User journeys

### Starting the day

1. Find the most recent daybook before today.
2. Create today's file with `date` frontmatter and the `## Tasks`, `## Learning` and `## Notes` headings.
3. Copy forward every task and learning item marked "yes" above, keeping the text exactly the same, under the same `### project` headings. Keep child note lines. Reset `[/]` to `[ ]`.
4. Drop project headings left with no tasks. Leave `## Notes` empty.
5. If today's file already exists, don't overwrite it. Tell the user instead.

### Summarizing accomplishments

Collect `[x]` tasks in the requested date range, grouped by project. Use child notes and `## Notes` for impact and context. Lead with the most significant work, not a chronological list.

### Reflecting on learning

Collect `## Learning` items in the date range: `[x]` as finished, `[/]` and `[ ]` as in progress. Use child notes for takeaways.

### Finding blockers

Find `[!]` tasks in the latest daybook. For each, trace back through earlier daybooks to the first day it was blocked, using the exact task text to match. Report how long it's been blocked and who it's waiting on, from child notes. Sort longest-blocked first.

### Other questions

Answer from the daybooks, citing the dates you drew on. Copy-forward rules mean an unfinished task appears on many days, so count it once.
