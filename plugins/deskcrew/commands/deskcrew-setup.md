---
description: Connect Claude Code to your DeskCrew workspace (one-time credential)
---

The user wants to connect Claude Code to their DeskCrew helpdesk. Guide them through the steps below. Do not paste or store their credential yourself; it belongs in their environment.

## Step 1 · Mint a credential (one time)

1. Sign in at https://deskcrew.io/dashboard (free workspace at https://deskcrew.io/signup if they do not have one).
2. Go to **Agents → Mint credential**. Choose the tools to allow. New credentials start at the **draft** tier: the agent can read tickets and file replies for a human to approve, but cannot send. An admin escalates specific tools later if wanted.
3. Copy the credential. It starts with `mcp_` and is shown once.

## Step 2 · Put it in the environment

The plugin's MCP server reads `DESKCREW_MCP_KEY`. Add to the shell profile (or the project's `.env` if Claude Code loads it):

```bash
export DESKCREW_MCP_KEY=mcp_…
```

Restart Claude Code so the plugin picks it up.

## Step 3 · Verify

1. Run `/mcp` and confirm `deskcrew` shows as **connected**.
2. Ask: "list my open DeskCrew tickets". The `list_tickets` tool should answer.
3. Ask for a reply to one ticket: the draft lands in the DeskCrew approval queue, and a human sends it from there.

## What it can do

The tools, and which ones change anything, are listed in the plugin README. Reading tickets and the knowledge base never changes anything. Drafts wait in the approval queue. Sending, resolving and assigning stay locked until an admin unlocks them for this credential.
