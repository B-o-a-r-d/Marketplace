---
key: notify
name: Notify (Slack / Discord)
repo: B-o-a-r-d/Notify-Plugin
package: board/plugin-notify
description: Post card events to Slack or Discord via an incoming webhook, as an automation action.
author: JibayMcs
homepage: https://github.com/B-o-a-r-d/Notify-Plugin
icon: chats-circle
capabilities: [automation-actions]
category: integrations
---
**Notify** adds a **“Notify Slack / Discord”** action to the automation builder,
so any trigger — card created, moved to a list, due date reached… — can post a
message to a chat channel.

- **Slack & Discord** — paste a `hooks.slack.com` or `discord.com/api/webhooks`
  incoming webhook; the platform is detected automatically.
- **Message template** — tokens `{title}`, `{list}`, `{board}`, `{due}`,
  `{completed}`; leave it empty for an automatic `"[Board] Card title — List"`.
- **Per-rule channel** — each automation rule stores its own webhook, so
  different rules can notify different channels.
- **Safe by design** — only Slack/Discord hosts are accepted, the request is
  SSRF-checked and pinned to the vetted IP, and the webhook URL and response are
  never logged. No board type, no OAuth, no extra infrastructure.
