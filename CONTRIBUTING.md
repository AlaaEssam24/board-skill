# Contributing

Thanks for helping improve the Board skill.

## Ways to contribute

- **Report a bad session.** Open an issue with the prompt you gave, what the board did, and what it should have done. Remove anything confidential first.
- **Improve a seat.** Seat briefs live in `skills/board/references/seats.md`. Keep the structure (mandate, principles, watches for, always asks, produces, hands to) and keep principles short, concrete and testable.
- **Propose a new seat.** Open an issue first. A new seat needs a function no existing seat owns, a clear "Active when" condition, and at least one natural opposition.

## Guidelines

- Seats are functions, not people. Do not add real names, personas or quotes as seat identities.
- Keep `SKILL.md` lean. Detail belongs in `references/`.
- Bump the version in `SKILL.md`, `.claude-plugin/plugin.json` and `.claude-plugin/marketplace.json`, and add a `CHANGELOG.md` entry.

## Pull requests

1. Fork the repo and create a branch.
2. Make the change and test it in Claude with at least one Quick and one Session prompt.
3. Describe what changed and paste a short before and after.
