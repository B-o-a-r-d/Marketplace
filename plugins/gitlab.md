---
key: gitlab
name: GitLab
repo: B-o-a-r-d/Gitlab-Plugin
description: Read-only commit / merge request / issue lists from a GitLab project, plus an MCP tool.
author: B-o-a-r-d
homepage: https://github.com/B-o-a-r-d/Gitlab-Plugin
icon: gitlab-logo
capabilities: [list-source, mcp-tools]
category: connectors
---
The **GitLab** Power-Up connects a board to a project.

- **Special lists** fed by a project's recent **commits**, open **merge requests** or
  open **issues** — read-only, lazy-loaded, refreshed live.
- **MCP tool** — list a project's recent commits from an AI agent.
- **Self-hosted GitLab** — set `GITLAB_URL` on the Board instance to point at your
  own GitLab (defaults to gitlab.com).

Requires connecting a GitLab OAuth application (scope `read_api`, configured per board,
credentials stored encrypted).
