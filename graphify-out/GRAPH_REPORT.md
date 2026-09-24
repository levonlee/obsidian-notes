# Graph Report - obsidian-notes  (2026-09-24)

## Corpus Check
- 44 files · ~3,890 words
- Verdict: corpus is large enough that graph structure adds value.
- Unclassified: 4 file(s) not represented in the graph (top: (none) 4)

## Summary
- 132 nodes · 146 edges · 27 communities (17 shown, 10 thin omitted)
- Extraction: 82% EXTRACTED · 18% INFERRED · 0% AMBIGUOUS · INFERRED: 27 edges (avg confidence: 0.79)
- Token cost: 0 input · 0 output

## Graph Freshness
- Built from commit: `8252d627`
- Run `git rev-parse HEAD` and compare to check if the graph is stale.
- Run `graphify update .` after code changes (no API cost).

## Community Hubs (Navigation)
- Claude Code configuration scopes (Managed > CLI > Local > Project > User)
- MySQL 8.0 to 8.4 upgrade
- Claude background sessions (claude --bg)
- PHP-FPM
- Weave stats
- Certificate Chain - Root vs Intermediate
- Git Reset Hard With Changing Branch
- Graphify (graphifyy)
- UV (Python)
- Git Submodule
- MCP 2026-07-28 spec support in Claude
- Ghostty SSH
- Tmux Copy Mode
- Screen Share
- getent hosts
- lsof -nP -i (macOS)
- Timezone
- Chrome Prompt API (built-in AI model)
- ClickHouse ports (8123 HTTP, 9000 native, 9004/9005 MySQL/PG emulation)
- Rider
- git add -f
- gitlab-ci-local (firecow)
- caffeinate -i
- apt-mark showhold
- Obsidian Hotkeys
- Transfer photos from iPhone to MacBook.md
- AGENTS.md

## God Nodes (most connected - your core abstractions)
1. `Claude Code configuration scopes (Managed > CLI > Local > Project > User)` - 8 edges
2. `Config Scope` - 7 edges
3. `MySQL 8.0 to 8.4 upgrade` - 6 edges
4. `.claude/settings.json` - 5 edges
5. `Codex configuration scope` - 5 edges
6. `Upgrade from 8.0 to 8.4` - 5 edges
7. `Claude background sessions (claude --bg)` - 5 edges
8. `PHP-FPM` - 5 edges
9. `Weave (developer productivity measurement)` - 5 edges
10. `Weave stats` - 5 edges

## Surprising Connections (you probably didn't know these)
- `MCP 2026-07-28 spec support in Claude` --conceptually_related_to--> `.mcp.json project MCP config`  [INFERRED]
  0 - Inbox/Claude MCP Announcement.md → 2 - Areas/AI/Claude/Config Scope.md
- `MCP 2026-07-28 spec support in Claude` --conceptually_related_to--> `sooperset mcp-atlassian (can read images)`  [INFERRED]
  0 - Inbox/Claude MCP Announcement.md → 2 - Areas/AI/MCPs/sooperset's mcp-atlassian.md
- `Claude Code Routines` --semantically_similar_to--> `Claude background sessions (claude --bg)`  [INFERRED] [semantically similar]
  2 - Areas/AI/Claude/Routine.md → 2 - Areas/AI/Claude/Agent View.md
- `CodeRabbit on GitLab` --conceptually_related_to--> `Code review dimensions (Purpose, Risk, Correctness & Logic, Readability, Architecture & Design)`  [INFERRED]
  2 - Areas/AI/CodeRabbit/Commands on GitLab.md → 0 - Inbox/Weave stats.md
- `graphify claude install (PreToolUse hooks + CLAUDE.md section)` --references--> `.claude/settings.json`  [INFERRED]
  2 - Areas/AI/Graphify.md → 2 - Areas/AI/Claude/Config Scope.md

## Hyperedges (group relationships)
- **Ways to run Claude Code sessions (background, remote, routines)** — 2___areas_ai_claude_agent_view_background_sessions, 2___areas_ai_claude_remote_control_remote_control, 2___areas_ai_claude_remote_control_server_mode, 2___areas_ai_claude_routine_claude_routines [INFERRED 0.75]
- **Updating branches without checkout** — 2___areas_git_branch_checkout_without_switching_git_fetch_refspec, 2___areas_git_git_reset_hard_with_changing_branch_git_push_force_with_lease_refspec, 2___areas_git_git_reset_hard_with_changing_branch_git_branch_force, 2___areas_git_branch_checkout_without_switching_git_branch_track [INFERRED 0.75]
- **Agent instruction/config files across Claude, Codex and Graphify** — claude, 2___areas_ai_openai_codex_config_scope_agents_md, 2___areas_ai_claude_config_scope_settings_json, 2___areas_ai_openai_codex_config_scope_codex_config_toml, 2___areas_ai_graphify_graphify_claude_install, 2___areas_ai_graphify_graphify_codex_install [INFERRED 0.85]
- **Nginx/PHP-FPM timeout layers causing truncated responses** — 2___areas_nginx_http_response_codes___500_vs_200_fastcgi_read_timeout, 2___areas_nginx_php_fpm_request_terminate_timeout, 2___areas_nginx_php_fpm_max_execution_time, 2___areas_nginx_http_response_codes___500_vs_200_truncated_200_response [INFERRED 0.85]
- **SSL certificate chain of trust** — 2___areas_ssl_certificate_chain___root_vs_intermediate_chain_of_trust, 2___areas_ssl_certificate_chain___root_vs_intermediate_root_certificate, 2___areas_ssl_certificate_chain___root_vs_intermediate_intermediate_certificate, 2___areas_ssl_ca_certificates_ca_certificates_bundle, 2___areas_ssl_ca_certificates_update_ca_certificates [INFERRED 0.85]

## Communities (27 total, 10 thin omitted)

### Community 0 - "Claude Code configuration scopes (Managed > CLI > Local > Project > User)"
Cohesion: 0.22
Nodes (15): Auto memory (~/.claude/projects/<project>/memory), Claude Code configuration scopes (Managed > CLI > Local > Project > User), ~/.claude.json (user and per-project MCPs), managed-settings.json (system managed, cannot be overridden), .mcp.json project MCP config, Config Scope, .claude/settings.json, AGENTS.md / AGENTS.override.md (+7 more)

### Community 1 - "MySQL 8.0 to 8.4 upgrade"
Cohesion: 0.27
Nodes (11): MySQL 8.0 to 8.4 upgrade, mysqlcheck --check-upgrade, Upgrade from 8.0 to 8.4, MySQL package hold check, Upgrade on production clone procedure, Ubuntu 20.04 to 22.04 upgrade prerequisite, EF Core migrations (dotnet ef), Idempotent migration SQL script (+3 more)

### Community 2 - "Claude background sessions (claude --bg)"
Cohesion: 0.29
Nodes (10): Claude background sessions (claude --bg), Model effort level (--effort), Agent View, Permission mode auto, sdk-cli sessions (CLAUDE_CODE_ENTRYPOINT=sdk-cli, Agent SDK), Remote Control, Claude Remote Control, Remote Control server mode (tmux + caffeinate loop) (+2 more)

### Community 3 - "PHP-FPM"
Cohesion: 0.24
Nodes (10): nginx -T (dump full config), Nginx: Check Values of Certain Configs, fastcgi_read_timeout, HTTP Response Codes - 500 vs 200, Truncated 200 Response, ignore_user_abort, max_execution_time, PHP-FPM (+2 more)

### Community 4 - "Weave stats"
Cohesion: 0.36
Nodes (9): Bugs per output unit, Jellyfish, Weave stats, Code review dimensions (Purpose, Risk, Correctness & Logic, Readability, Architecture & Design), Weave (developer productivity measurement), Weekly Revert Rate, CodeRabbit on GitLab, Commands on GitLab (+1 more)

### Community 5 - "Certificate Chain - Root vs Intermediate"
Cohesion: 0.28
Nodes (9): /etc/ssl/certs/ca-certificates.crt bundle, CA Certificates, openssl x509 / s_client inspection, update-ca-certificates, Chain of Trust (end-user > intermediate > root), CSR (Certificate Signing Request), Intermediate Certificate, Certificate Chain - Root vs Intermediate (+1 more)

### Community 6 - "Git Reset Hard With Changing Branch"
Cohesion: 0.33
Nodes (7): git branch --track, git fetch origin src:dst refspec (fast-forward / forced +), Branch Checkout Without Switching, git branch -f, git push --force-with-lease origin HEAD:refs/heads/staging, git reset --hard, Git Reset Hard With Changing Branch

### Community 7 - "Graphify (graphifyy)"
Cohesion: 0.60
Nodes (6): Graphify (graphifyy), graphify claude install (PreToolUse hooks + CLAUDE.md section), graphify codex install (AGENTS.md + .codex/hooks.json), graphify hook install (git post-commit/post-checkout, merge driver), .graphifyignore, Graphify

### Community 8 - "UV (Python)"
Cohesion: 0.40
Nodes (6): graphifyy tool, UV (Python), Python major.minor.patch versioning, uv python install / upgrade, uv python pin (.python-version), uv tool install --python

### Community 9 - "Git Submodule"
Cohesion: 0.50
Nodes (5): git submodule status (- / + prefixes), git submodule update --init --recursive, git submodule update --remote, .gitmodules file (branch setting), Git Submodule

### Community 10 - "MCP 2026-07-28 spec support in Claude"
Cohesion: 0.50
Nodes (4): MCP 2026-07-28 spec support in Claude, Claude MCP Announcement, sooperset mcp-atlassian (can read images), sooperset's mcp-atlassian

### Community 11 - "Ghostty SSH"
Cohesion: 0.50
Nodes (4): Ghostty SSH, xterm-ghostty terminfo on remote servers, Maximize split pane (Cmd+Shift+Enter), Maximize a Split Pane

### Community 12 - "Tmux Copy Mode"
Cohesion: 0.50
Nodes (4): mode-keys (emacs vs vi), Tmux Copy Mode, Tmux Basics, Tmux sessions (new/detach/attach/ls)

### Community 13 - "Screen Share"
Cohesion: 0.67
Nodes (3): macOS Screen Sharing setting, Screen Share, Tailscale

### Community 14 - "getent hosts"
Cohesion: 0.67
Nodes (3): getent hosts, Ubuntu Network, NSS (Name Service Switch)

### Community 15 - "lsof -nP -i (macOS)"
Cohesion: 1.00
Nodes (3): lsof -nP -i (macOS), Ports, ss -lntup (Linux)

### Community 16 - "Timezone"
Cohesion: 0.67
Nodes (3): cron restart after timezone change, Timezone, timedatectl set-timezone

## Knowledge Gaps
- **47 isolated node(s):** `Transfer photos from iPhone to MacBook`, `graphify`, `graphify`, `Superpowers Marketplace`, `Install` (+42 more)
  These have ≤1 connection - possible missing edges or undocumented components. (Counts symbols only; 49 node(s) total have ≤1 connection when file, concept and rationale nodes are included.)
- **10 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `.claude/settings.json` connect `Claude Code configuration scopes (Managed > CLI > Local > Project > User)` to `Graphify (graphifyy)`?**
  _High betweenness centrality (0.010) - this node is a cross-community bridge._
- **Why does `.mcp.json project MCP config` connect `Claude Code configuration scopes (Managed > CLI > Local > Project > User)` to `MCP 2026-07-28 spec support in Claude`?**
  _High betweenness centrality (0.010) - this node is a cross-community bridge._
- **Are the 2 inferred relationships involving `.claude/settings.json` (e.g. with `graphify claude install (PreToolUse hooks + CLAUDE.md section)` and `Superpowers plugin marketplace (obra/Superpowers)`) actually correct?**
  _`.claude/settings.json` has 2 INFERRED edges - model-reasoned connections that need verification._
- **What connects `Transfer photos from iPhone to MacBook`, `graphify`, `graphify` to the rest of the system?**
  _47 weakly-connected nodes found - possible documentation gaps or missing edges._