<h1 align="center">Board Marketplace</h1>

<p align="center">The curated catalog of <a href="https://github.com/B-o-a-r-d/board">Board</a> Power-Ups.</p>

---

Each plugin is one markdown file in [`plugins/`](plugins) with YAML front-matter.
A Board instance (with the marketplace enabled) reads this catalog and lets admins
**install Power-Ups at runtime** — no redeploy — pinned to the plugin's GitHub
**releases**.

- **Add or update a plugin?** Fork this repo, add/edit `plugins/<key>.md`, open a PR.
  It's merged after review. See **[CONTRIBUTING.md](CONTRIBUTING.md)**.
- **Trust model:** only plugins listed here are installable, and only from their
  declared repository at tagged releases. Installing runs third-party PHP in-process,
  so this catalog is curated and reviewed.

## Entry format

```markdown
---
key: github                      # unique plugin key (matches Plugin::key())
name: GitHub
repo: owner/repo                  # the plugin's GitHub repository
description: One-line summary.
author: your-handle
homepage: https://github.com/owner/repo
icon: github-logo                # a Phosphor icon name
capabilities: [list-source, card-enrichment, activities, mcp-tools]
category: connectors
---
A longer markdown description shown on the plugin's marketplace page.
```

Build a plugin: see the [Board wiki → Creating a plugin](https://github.com/B-o-a-r-d/board/wiki/Creating-a-Plugin).
