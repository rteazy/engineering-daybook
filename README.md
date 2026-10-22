# Daybook
Definition of an agent-friendly [engineering daybook.](https://www.oreilly.com/library/view/the-pragmatic-programmer/9780135956977/f_0041.xhtml)

## Daylog format

- Frontmatter: `date: YYYY-MM-DD`.
- `## Tasks`: checklist grouped by `### project` headings. Each day, copy forward every task that isn't `[x]` or `[-]`, keeping the text exactly the same.
- Indented child lines under a task are notes about it. Reports may use them.
- `## Notes`: free-form notes not tied to a task. Never used in reports.
- `## Learning`: checklist of what you're reading or learning. Uses the same task states and copy-forward rule as Tasks, and child lines hold takeaways. Not counted as task-days and never used in reports, but you can query it (e.g. "what have I read about locking?", "how many learning days in October?").

## Task states

| Box   | Meaning     |
|-------|-------------|
| `[ ]` | open        |
| `[/]` | worked on today |
| `[x]` | done        |
| `[!]` | blocked     |
| `[-]` | dropped     |


## Examples

- Daylog: [example-daylog.md](example-daylog.md)
- Weekly report: [example-weekly-report.md](example-weekly-report.md)
