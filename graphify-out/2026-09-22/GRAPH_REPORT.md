# Graph Report - obsidian-notes  (2026-09-22)

## Corpus Check
- Corpus is ~3,323 words - fits in a single context window. You may not need a graph.

## Summary
- 127 nodes · 143 edges · 25 communities (17 shown, 8 thin omitted)
- Extraction: 81% EXTRACTED · 19% INFERRED · 0% AMBIGUOUS · INFERRED: 27 edges (avg confidence: 0.79)
- Token cost: 94,678 input · 0 output

## Community Hubs (Navigation)
- Agent Config Scopes
- DB Upgrades & Migrations
- Claude Session Modes
- Nginx PHP-FPM Timeouts
- Code Review Metrics
- SSL Chain of Trust
- Git Branch Updates
- Graphify Setup
- UV Python Tooling
- Git Submodules
- MCP Integrations
- Ghostty Terminal
- Tmux
- macOS Screen Sharing
- Ubuntu Name Resolution
- Listening Ports
- Ubuntu Timezone
- Chrome Built-in AI
- ClickHouse Ports
- Rider Keymap
- Git Force Add
- GitLab CI Local
- Keep Mac Awake
- Apt Package Holds
- Obsidian Hotkeys

## God Nodes (most connected - your core abstractions)
1. `Claude Code configuration scopes (Managed > CLI > Local > Project > User)` - 8 edges
2. `Config Scope` - 7 edges
3. `MySQL 8.0 to 8.4 upgrade` - 6 edges
4. `Weave stats` - 5 edges
5. `Graphify` - 5 edges
6. `Upgrade from 8.0 to 8.4` - 5 edges
7. `Weave (developer productivity measurement)` - 5 edges
8. `Claude background sessions (claude --bg)` - 5 edges
9. `.claude/settings.json` - 5 edges
10. `Graphify (graphifyy)` - 5 edges

## Surprising Connections (you probably didn't know these)
- `MCP 2026-07-28 spec support in Claude` --conceptually_related_to--> `.mcp.json project MCP config`  [INFERRED]
  0 - Inbox/Claude MCP Announcement.md → 2 - Areas/AI/Claude/Config Scope.md
- `MCP 2026-07-28 spec support in Claude` --conceptually_related_to--> `sooperset mcp-atlassian (can read images)`  [INFERRED]
  0 - Inbox/Claude MCP Announcement.md → 2 - Areas/AI/MCPs/sooperset's mcp-atlassian.md
- `CodeRabbit on GitLab` --conceptually_related_to--> `Code review dimensions (Purpose, Risk, Correctness & Logic, Readability, Architecture & Design)`  [INFERRED]
  2 - Areas/AI/CodeRabbit/Commands on GitLab.md → 0 - Inbox/Weave stats.md
- `Claude Code Routines` --semantically_similar_to--> `Claude background sessions (claude --bg)`  [INFERRED] [semantically similar]
  2 - Areas/AI/Claude/Routine.md → 2 - Areas/AI/Claude/Agent View.md
- `Codex configuration scope` --semantically_similar_to--> `Claude Code configuration scopes (Managed > CLI > Local > Project > User)`  [INFERRED] [semantically similar]
  2 - Areas/AI/OpenAI/Codex Config Scope.md → 2 - Areas/AI/Claude/Config Scope.md

## Hyperedges (group relationships)
- **Agent instruction/config files across Claude, Codex and Graphify** — 2___areas_ai_claude_config_scope_claude_md, 2___areas_ai_openai_codex_config_scope_agents_md, 2___areas_ai_claude_config_scope_settings_json, 2___areas_ai_openai_codex_config_scope_codex_config_toml, 2___areas_ai_graphify_graphify_claude_install, 2___areas_ai_graphify_graphify_codex_install [INFERRED 0.85]
- **Ways to run Claude Code sessions (background, remote, routines)** — 2___areas_ai_claude_agent_view_background_sessions, 2___areas_ai_claude_remote_control_remote_control, 2___areas_ai_claude_remote_control_server_mode, 2___areas_ai_claude_routine_claude_routines [INFERRED 0.75]
- **Nginx/PHP-FPM timeout layers causing truncated responses** — 2___areas_nginx_http_response_codes___500_vs_200_fastcgi_read_timeout, 2___areas_nginx_php_fpm_request_terminate_timeout, 2___areas_nginx_php_fpm_max_execution_time, 2___areas_nginx_http_response_codes___500_vs_200_truncated_200_response [INFERRED 0.85]
- **SSL certificate chain of trust** — 2___areas_ssl_certificate_chain___root_vs_intermediate_chain_of_trust, 2___areas_ssl_certificate_chain___root_vs_intermediate_root_certificate, 2___areas_ssl_certificate_chain___root_vs_intermediate_intermediate_certificate, 2___areas_ssl_ca_certificates_ca_certificates_bundle, 2___areas_ssl_ca_certificates_update_ca_certificates [INFERRED 0.85]
- **Updating branches without checkout** — 2___areas_git_branch_checkout_without_switching_git_fetch_refspec, 2___areas_git_git_reset_hard_with_changing_branch_git_push_force_with_lease_refspec, 2___areas_git_git_reset_hard_with_changing_branch_git_branch_force, 2___areas_git_branch_checkout_without_switching_git_branch_track [INFERRED 0.75]

## Communities (25 total, 8 thin omitted)

### Community 0 - "Agent Config Scopes"
Cohesion: 0.24
Nodes (15): Auto memory (~/.claude/projects/<project>/memory), Claude Code configuration scopes (Managed > CLI > Local > Project > User), ~/.claude.json (user and per-project MCPs), CLAUDE.md, managed-settings.json (system managed, cannot be overridden), .mcp.json project MCP config, Config Scope, .claude/settings.json (+7 more)

### Community 1 - "DB Upgrades & Migrations"
Cohesion: 0.27
Nodes (11): MySQL 8.0 to 8.4 upgrade, mysqlcheck --check-upgrade, Upgrade from 8.0 to 8.4, MySQL package hold check, Upgrade on production clone procedure, Ubuntu 20.04 to 22.04 upgrade prerequisite, EF Core migrations (dotnet ef), Idempotent migration SQL script (+3 more)

### Community 2 - "Claude Session Modes"
Cohesion: 0.29
Nodes (10): Claude background sessions (claude --bg), Model effort level (--effort), Agent View, Permission mode auto, sdk-cli sessions (CLAUDE_CODE_ENTRYPOINT=sdk-cli, Agent SDK), Remote Control, Claude Remote Control, Remote Control server mode (tmux + caffeinate loop) (+2 more)

### Community 3 - "Nginx PHP-FPM Timeouts"
Cohesion: 0.24
Nodes (10): nginx -T (dump full config), Nginx: Check Values of Certain Configs, fastcgi_read_timeout, HTTP Response Codes - 500 vs 200, Truncated 200 Response, ignore_user_abort, max_execution_time, PHP-FPM (+2 more)

### Community 4 - "Code Review Metrics"
Cohesion: 0.36
Nodes (9): Bugs per output unit, Jellyfish, Weave stats, Code review dimensions (Purpose, Risk, Correctness & Logic, Readability, Architecture & Design), Weave (developer productivity measurement), Weekly Revert Rate, CodeRabbit on GitLab, Commands on GitLab (+1 more)

### Community 5 - "SSL Chain of Trust"
Cohesion: 0.28
Nodes (9): /etc/ssl/certs/ca-certificates.crt bundle, CA Certificates, openssl x509 / s_client inspection, update-ca-certificates, Chain of Trust (end-user > intermediate > root), CSR (Certificate Signing Request), Intermediate Certificate, Certificate Chain - Root vs Intermediate (+1 more)

### Community 6 - "Git Branch Updates"
Cohesion: 0.33
Nodes (7): git branch --track, git fetch origin src:dst refspec (fast-forward / forced +), Branch Checkout Without Switching, git branch -f, git push --force-with-lease origin HEAD:refs/heads/staging, git reset --hard, Git Reset Hard With Changing Branch

### Community 7 - "Graphify Setup"
Cohesion: 0.60
Nodes (6): Graphify (graphifyy), graphify claude install (PreToolUse hooks + CLAUDE.md section), graphify codex install (AGENTS.md + .codex/hooks.json), graphify hook install (git post-commit/post-checkout, merge driver), .graphifyignore, Graphify

### Community 8 - "UV Python Tooling"
Cohesion: 0.40
Nodes (6): graphifyy tool, UV (Python), Python major.minor.patch versioning, uv python install / upgrade, uv python pin (.python-version), uv tool install --python

### Community 9 - "Git Submodules"
Cohesion: 0.50
Nodes (5): git submodule status (- / + prefixes), git submodule update --init --recursive, git submodule update --remote, .gitmodules file (branch setting), Git Submodule

### Community 10 - "MCP Integrations"
Cohesion: 0.50
Nodes (4): MCP 2026-07-28 spec support in Claude, Claude MCP Announcement, sooperset mcp-atlassian (can read images), sooperset's mcp-atlassian

### Community 11 - "Ghostty Terminal"
Cohesion: 0.50
Nodes (4): Ghostty SSH, xterm-ghostty terminfo on remote servers, Maximize split pane (Cmd+Shift+Enter), Maximize a Split Pane

### Community 12 - "Tmux"
Cohesion: 0.50
Nodes (4): mode-keys (emacs vs vi), Tmux Copy Mode, Tmux Basics, Tmux sessions (new/detach/attach/ls)

### Community 13 - "macOS Screen Sharing"
Cohesion: 0.67
Nodes (3): macOS Screen Sharing setting, Screen Share, Tailscale

### Community 14 - "Ubuntu Name Resolution"
Cohesion: 0.67
Nodes (3): getent hosts, Ubuntu Network, NSS (Name Service Switch)

### Community 15 - "Listening Ports"
Cohesion: 1.00
Nodes (3): lsof -nP -i (macOS), Ports, ss -lntup (Linux)

### Community 16 - "Ubuntu Timezone"
Cohesion: 0.67
Nodes (3): cron restart after timezone change, Timezone, timedatectl set-timezone

## Knowledge Gaps
- **44 isolated node(s):** `Chrome has an AI model`, `Claude MCP Announcement`, `Routine`, `sooperset's mcp-atlassian`, `Superpowers Marketplace` (+39 more)
  These have ≤1 connection - possible missing edges or undocumented components. (Counts symbols only; 44 node(s) total have ≤1 connection when file, concept and rationale nodes are included.)
- **8 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `.claude/settings.json` connect `Agent Config Scopes` to `Graphify Setup`?**
  _High betweenness centrality (0.011) - this node is a cross-community bridge._
- **Why does `.mcp.json project MCP config` connect `Agent Config Scopes` to `MCP Integrations`?**
  _High betweenness centrality (0.010) - this node is a cross-community bridge._
- **What connects `Chrome has an AI model`, `Claude MCP Announcement`, `Routine` to the rest of the system?**
  _44 weakly-connected nodes found - possible documentation gaps or missing edges._