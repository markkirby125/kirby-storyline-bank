# kirby-storyline-bank

*This skill is part of the [Tiffany Lambert PLR Skills Collection](https://github.com/markkirby125/kirby-skills-tiff-collection).*

A structured system for eliciting, structuring, cataloguing, and retrieving personal business scars, client breakthroughs, and life lessons into a queryable Storyline Bank to anchor AI writing in authentic human experience.

## 🪄 The Magic Prompt

Copy and paste this directly to your AI (Cursor, Windsurf, Claude Code, Antigravity):

```markdown
@agent Please install the kirby-storyline-bank skill into this workspace.
1. Read the `SKILL.md` file (and `references/` directory) from this repository: https://github.com/markkirby125/kirby-storyline-bank
2. Identify the correct rules system for our current environment (e.g., `.cursor/rules/` for Cursor, `.windsurfrules` for Windsurf, `.clinerules` for Cline, or `~/.agents/skills/` for Antigravity).
3. Save the contents appropriately, preserving the multi-file dispatcher structure.
4. Confirm when the installation is complete.
```

## Manual Installation

- **Cursor**: Save `SKILL.md` to `.cursor/rules/kirby-storyline-bank.mdc`
- **Windsurf**: Save `SKILL.md` to `.windsurfrules`
- **Antigravity / Agent CLIs**: Clone this repository into `~/.agents/skills/kirby-storyline-bank`

## Tech Stack

- **Format**: Markdown / JSON Storyline Schema
- **Compatibility**: Antigravity, Claude Code, Cursor, Windsurf, Cline
