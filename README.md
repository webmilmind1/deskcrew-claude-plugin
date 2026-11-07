<!-- deskcrew-header:start -->
<p align="center">
  <a href="https://deskcrew.io"><img src="https://deskcrew.io/logo.png" alt="DeskCrew" width="96" height="96"></a>
</p>

<h1 align="center">DeskCrew for Claude Code</h1>

<p align="center"><b>DeskCrew for Claude Code</b></p>

<p align="center">Helpdesk MCP server for Claude Code: tickets, replies drafted for a person to approve, and your knowledge base and changelog.</p>

<p align="center">
  <a href="https://deskcrew.io"><b>Website</b></a> •
  <a href="https://deskcrew.io/integrations"><b>Integrations</b></a> •
  <a href="https://deskcrew.io/help"><b>Help center</b></a> •
  <a href="https://deskcrew.io/signup"><b>Sign up</b></a>
</p>

<p align="center">
  <a href="https://github.com/webmilmind1/deskcrew-claude-plugin/stargazers"><img src="https://img.shields.io/github/stars/webmilmind1/deskcrew-claude-plugin?style=flat&logo=github&label=Stars&color=ffd33d" alt="GitHub stars"></a>
  <a href="https://github.com/webmilmind1/deskcrew-claude-plugin"><img src="https://img.shields.io/github/license/webmilmind1/deskcrew-claude-plugin?style=flat&label=License&color=e3a82b" alt="License"></a>
</p>

<p align="center">
  <a href="https://deskcrew.io"><img src="https://img.shields.io/badge/Visit_our_website-6366F1?style=for-the-badge&logoColor=white" alt="Visit our website"></a>
  <a href="https://discord.gg/hdWZgrYDqB"><img src="https://img.shields.io/badge/Join_our_Discord-5865F2?style=for-the-badge&logoColor=white&logo=discord" alt="Join our Discord"></a>
  <a href="https://x.com/getdeskcrew"><img src="https://img.shields.io/badge/Follow_%40getdeskcrew-000000?style=for-the-badge&logoColor=white&logo=x" alt="Follow @getdeskcrew"></a>
  <a href="https://whop.com/deskcrew/"><img src="https://img.shields.io/badge/Join_us_on_Whop-FF6243?style=for-the-badge&logoColor=white" alt="Join us on Whop"></a>
</p>

<p align="center"><i>⭐ Help more people find DeskCrew. Star this repo!</i></p>
<!-- deskcrew-header:end -->

Connects Claude Code to [DeskCrew](https://deskcrew.io): a helpdesk with live chat, email, Slack and Discord tickets in one inbox, and a knowledge base your answers are grounded in.

## What you get

- **MCP server** (`deskcrew`, `https://deskcrew.io/api/helpdesk/mcp`): read tickets, draft replies for human approval, search and publish knowledge base and changelog entries, and manage roadmap issues. Draft-first by design: a new credential cannot send anything to a customer until an admin unlocks sending for it.
- **`/deskcrew-setup`**: the one-time credential walkthrough.
- **Skill** `deskcrew-support`: how to work a support queue one ticket at a time, answer from the knowledge base, and leave the reply for a person to approve.

## Install

```bash
claude plugin marketplace add webmilmind1/deskcrew-claude-plugin
claude plugin install deskcrew
```

Then run `/deskcrew-setup`.

## Tools

Every tool carries a title and MCP hints. **Read-only** tools never change anything. **Destructive** marks tools that overwrite content or reach a customer. Send-tier tools are refused until a workspace admin unlocks them for the credential.

| Tool | What it does | Read-only | Destructive |
| --- | --- | --- | --- |
| `list_tickets` | List tickets, filtered by status, priority or age | yes | no |
| `search_tickets` | Full-text search across tickets | yes | no |
| `get_ticket_context` | Read one ticket's full conversation | yes | no |
| `search_kb` | Search the knowledge base | yes | no |
| `read_kb` | Read one knowledge base article | yes | no |
| `list_kb_categories` | List knowledge base categories | yes | no |
| `list_issues` | List roadmap issues | yes | no |
| `list_changelog` | List changelog entries | yes | no |
| `list_reports` | List the workspace's reports | yes | no |
| `get_report` | Run one report | yes | no |
| `triage` | Set a ticket's priority, tags or category | no | no |
| `draft_reply` | Save a reply as a draft for a person to approve; nothing is sent | no | no |
| `propose_resolution` | Save a proposed resolution as a draft for approval | no | no |
| `link_issue` | Link a ticket to a roadmap issue | no | no |
| `create_ticket` | Create a ticket | no | no |
| `create_issue` | Create a roadmap issue | no | no |
| `update_issue` | Update a roadmap issue's status or details | no | yes |
| `create_kb` | Publish a knowledge base article | no | no |
| `update_kb` | Edit a knowledge base article | no | yes |
| `create_kb_category` | Create a knowledge base category | no | no |
| `create_changelog` | Publish a changelog entry | no | no |
| `send_reply` | Send a reply to the customer (send tier, locked by default) | no | yes |
| `resolve` | Resolve a ticket and notify the customer (send tier, locked by default) | no | yes |
| `assign` | Assign a ticket to a teammate (send tier, locked by default) | no | no |

## Credential and data

The MCP server reads `DESKCREW_MCP_KEY` from your environment and sends it only to `https://deskcrew.io/api/helpdesk/mcp` over HTTPS. Credentials are created and revoked per agent in the DeskCrew dashboard, are bound to one workspace, and are limited per tool.

Privacy policy: https://deskcrew.io/privacy

## Links

- Website: https://deskcrew.io
- Help center: https://deskcrew.io/help
- Sign up: https://deskcrew.io/signup

MIT licensed.
