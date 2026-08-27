## Install
https://github.com/Graphify-Labs/graphify#install

```sh
uv tool install --python 3.14 graphifyy
uv tool list --show-paths
```

```
graphifyy v0.9.34 (/Users/lili/.local/share/uv/tools/graphifyy)
- graphify (/Users/lili/.local/bin/graphify)
- graphify-mcp (/Users/lili/.local/bin/graphify-mcp)
```

```sh
cd ~/myproject
# this is for Claude
graphify install
```

```
 references       ->  /Users/lili/.claude/skills/graphify/references
  skill installed  ->  /Users/lili/.claude/skills/graphify/SKILL.md
  CLAUDE.md        ->  skill registered in /Users/lili/.claude/CLAUDE.md

Done. Open your AI coding assistant and type:

  /graphify .
```

```sh
graphify install --platform codex
```

```
  references       ->  /Users/lili/.codex/skills/graphify/references
  skill installed  ->  /Users/lili/.codex/skills/graphify/SKILL.md

Done. Open your AI coding assistant and type:

  /graphify .
```

This will create `~/myproject/graphify-out/` and `~/myproject/.graphifyignore`

Then run:
```sh
graphify claude install
```

Results:
- `.claude/settings.json` is on project level not user level

```
➜  ~/myproject graphify claude install
graphify section written to /Users/lili/ma/myproject/CLAUDE.md
  .claude/settings.json  ->  PreToolUse hooks registered (Bash|Grep search + Read/Glob)

Claude Code will now check the knowledge graph before answering
codebase questions and rebuild it after code changes.
```

```
➜  ~/myproject graphify codex install
graphify section written to /Users/lili/myproject/AGENTS.md
  .codex/hooks.json  ->  PreToolUse hook registered (/Users/lili/.local/bin/graphify hook-check - intentional no-op; Codex Desktop rejects additionalContext on PreToolUse, so graph guidance comes from AGENTS.md)

Codex will now check the knowledge graph before answering
codebase questions and rebuild it after code changes.
```

### `graphify hook install`
It will modify the following in `/myproject/.git/hooks`:
- post-commit
- post-checkout

And add a line in `/myproject/.gitattributes` to instruct to use the `graphify` driver to merge this file `graphify-out/graph.json`

**If you reinstall or upgrade graphify, re-run `graphify hook install` to refresh the embedded path.**

## Remove or Add More Files to Graph

After you delete a line in `.graphifyignore`, you need to run `/graphify . --update`
Adding a line `.graphifyignore`, you need to rebuild: `rm graphify-out/graph.json` and then run `/graphify .`
