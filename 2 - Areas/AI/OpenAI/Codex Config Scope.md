## Config
- `~/.codex/config.toml` like `~/.claude/settings.json`

## Skills
	- `$CWD/.agents/skills`
	- `$CWD/../.agents/skills`
	- `$REPO_ROOT/.agents/skills`
	- `$HOME/.agents/skills`
	- `/etc/codex/skills`
	- `$HOME/.codex/skills/.system/`

## AGENTS.md
There's no AGENTS.local.md, instead there's `AGENTS.override.md` which overrides. You can do this:

```md
@AGENTS.md

Your customization...
```