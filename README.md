# [plugin-name]

> Claude Code plugin template

## Overview

[Describe what this plugin does and who it's for.]

## Getting started

1. Click **Use this template** to create a new repository.
2. Replace every `[plugin-name]` placeholder with your plugin's name.
3. Fill in `.claude-plugin/plugin.json` with your plugin details.
4. Validate the plugin with `claude plugin validate`.

## Repository structure

```
.
├── .claude-plugin/
│   └── plugin.json        # Plugin manifest (name, version, description)
└── .github/
    └── workflows/
        ├── CI.yml                 # Validates JSON + checks manifest
        ├── claude.yml             # Runs Claude on @claude mentions
        └── claude-code-review.yml # Auto code review on PRs
```

## Secrets required

| Secret                    | Required for                           |
| ------------------------- | -------------------------------------- |
| `CLAUDE_CODE_OAUTH_TOKEN` | `claude.yml`, `claude-code-review.yml` |

Set these under **Settings → Secrets and variables → Actions**.

## Resources

- [Claude Code plugin docs](https://code.claude.com/docs/en/plugins)
- [Plugin reference](https://code.claude.com/docs/en/plugins-reference)
- [claude-code-action](https://github.com/anthropics/claude-code-action)
