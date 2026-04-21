# [plugin-name]

Claude Code plugin template repository.

## Commands

Validate plugin:

```bash
claude plugin validate
```

Lint Markdown:

```bash
npx markdownlint-cli "**/*.md" --ignore node_modules
```

Lint YAML:

```bash
yamllint -d relaxed .
```

## Structure

```text
.claude-plugin/plugin.json   # Plugin manifest (name, version, description, author)
skills/<name>/SKILL.md       # Skill definition — one folder per skill
hooks/                       # (optional) Hook definitions
commands/                    # (optional) Slash command definitions
```

## Adding a skill

1. Create `skills/<skill-name>/SKILL.md`
2. Add frontmatter — `description:` is required
   (Claude uses it to decide when to invoke)
3. Invoke via `/[plugin-name]:<skill-name>`

## Secrets required

| Secret                    | Used by                                       |
| ------------------------- | --------------------------------------------- |
| `CLAUDE_CODE_OAUTH_TOKEN` | `claude.yml`, `claude-code-review.yml`        |
| `MY_RELEASE_PLEASE_TOKEN` | `CI.yml` `tag` job (PAT — contents:write)     |

## CI checks (`CI.yml`)

- **markdownlint**: `**/*.md`
- **JSON validity**: all `.json` files must parse
- **yamllint** (relaxed): all YAML files
- **Manifest**: `.claude-plugin/plugin.json` must exist
