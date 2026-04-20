# [plugin-name]

Claude Code plugin template repository.

## Commands

Validate plugin:

```bash
claude plugin validate
```

Check formatting (matches CI):

```bash
npx prettier --check "**/*.{md,json,yml,yaml}"
```

Fix formatting:

```bash
npx prettier --write "**/*.{md,json,yml,yaml}"
```

## Structure

```
.claude-plugin/plugin.json   # Plugin manifest (name, version, description, author)
skills/<name>/SKILL.md       # Skill definition — one folder per skill
hooks/                       # (optional) Hook definitions
commands/                    # (optional) Slash command definitions
```

## Adding a skill

1. Create `skills/<skill-name>/SKILL.md`
2. Add frontmatter — `description:` is required (Claude uses it to decide when to invoke)
3. Invoke via `/[plugin-name]:<skill-name>`

## Secrets required

| Secret                    | Used by                                          |
| ------------------------- | ------------------------------------------------ |
| `CLAUDE_CODE_OAUTH_TOKEN` | `claude.yml`, `claude-code-review.yml`           |
| `MY_RELEASE_PLEASE_TOKEN` | `release-please.yml` (PAT — repo/issue/PR write) |

## CI checks

- **Prettier**: `**/*.{md,json,yml,yaml}` — install globally or use `npx prettier` locally
- **JSON validity**: all `.json` files must parse cleanly
- **Manifest**: `.claude-plugin/plugin.json` must exist
