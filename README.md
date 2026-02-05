# Claude Elements

My Claude Code configuration backup: guidelines, skills, hooks, and settings.

## Structure

```
claude-elements/
├── CLAUDE.md                    # Global project guidelines
├── config/
│   ├── settings.json.template   # Settings template (tokens redacted)
│   └── settings.local.json      # Local permissions
├── commands/
│   └── interview.md             # Custom /interview command
└── skills/
    ├── commit/
    │   └── SKILL.md             # Commit skill
    └── frontend-slides/
        ├── skill.md             # HTML presentation generator
        └── STYLE_PRESETS.md     # Visual style presets
```

## Installation

### CLAUDE.md
Copy to your project root or `~/claude/CLAUDE.md` for global use:
```bash
cp CLAUDE.md ~/claude/CLAUDE.md
```

### Settings
Copy and customize with your tokens:
```bash
cp config/settings.json.template ~/.claude/settings.json
# Edit ~/.claude/settings.json and add your tokens
```

### Commands
```bash
mkdir -p ~/.claude/commands
cp commands/*.md ~/.claude/commands/
```

### Skills
```bash
cp -r skills/* ~/.claude/skills/
```

## Key Features

### CLAUDE.md Guidelines
- **Core Principles**: Simplicity first, no laziness, minimal impact
- **Plan Mode Default**: Enter plan mode for non-trivial tasks
- **Subagent Strategy**: Use subagents to keep context clean
- **TDD (When Appropriate)**: Propose test-driven development
- **Verification Before Done**: Prove it works before marking complete

### Hooks
- **PostToolUse/Edit**: Runs TypeScript type checking after file edits

### MCP Servers
- Slack integration
- GitHub integration
- Memory - persistent knowledge graph across sessions

### Custom Commands
- `/interview` - In-depth user interview to create detailed specs

### Skills
- `commit` - Review changes and write conventional commits
- `frontend-slides` - Create animation-rich HTML presentations
