# Changelog

All notable changes to the daybook format are documented here.
This project uses [Semantic Versioning](https://semver.org).

## [1.1.0] - 2026-10-24

### Added
- `daybook` skill in the open Agent Skills format.

### Changed
- `[/]` tasks reset to `[ ]` when copied forward.
- Format spec moved from the README to `skills/daybook/SKILL.md`.
- Example daybook moved to `skills/daybook/references/`.

## [1.0.0] - 2026-10-24

### Added
- Daybook format: one Markdown file per day named `YYYY-MM-DD.md`, with `date` frontmatter and `## Tasks`, `## Learning` and `## Notes` sections.
- Task states: open, worked on today, blocked, done and dropped, with copy-forward rules.
- User journeys: example LLM prompts for working with your daybooks.
- Example daybook.
