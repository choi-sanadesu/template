# [plugin-name]

> Claude Code plugin template

## Overview

[Describe what this plugin does and who it's for.]

## Getting started

1. Click **Use this template** to create a new repository.
2. Replace every `[plugin-name]` placeholder with your plugin's name.
3. Fill in `.claude-plugin/plugin.json` with your plugin details.
4. Add skills inside `skills/`, one folder per skill.
5. (Optional) Add hooks in `hooks/` and commands in `commands/`.
6. Validate the plugin with `claude plugin validate`.

## Repository structure

```
.
├── .claude-plugin/
│   └── plugin.json        # Plugin manifest (name, version, description)
├── skills/
│   └── example-skill/
│       └── SKILL.md       # Skill definition and instructions
├── hooks/                 # (optional) Hook definitions
├── commands/              # (optional) Slash command definitions
└── .github/
    └── workflows/
        ├── CI.yml                 # Validates JSON + checks manifest
        ├── claude.yml             # Runs Claude on @claude mentions
        └── claude-code-review.yml # Auto code review on PRs
```

## Secrets required

| Secret | Required for |
|--------|-------------|
| `CLAUDE_CODE_OAUTH_TOKEN` | `claude.yml`, `claude-code-review.yml` |

Set these under **Settings → Secrets and variables → Actions**.

## Writing a skill

Create a folder under `skills/` with a `SKILL.md` file:

```
skills/
└── my-skill/
    └── SKILL.md
```

**`SKILL.md` format:**

```markdown
---
description: One-line description — Claude uses this to decide when to invoke this skill.
---

# Skill Name

Instructions for Claude...
```

Invoked via: `/[plugin-name]:my-skill`

## Resources

- [Claude Code plugin docs](https://code.claude.com/docs/en/plugins)
- [Plugin reference](https://code.claude.com/docs/en/plugins-reference)
- [claude-code-action](https://github.com/anthropics/claude-code-action)
