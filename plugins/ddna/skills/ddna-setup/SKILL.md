---
name: ddna-setup
description: Connect or reconnect DDNA in Claude, ChatGPT, or Codex by signing in to an existing DDNA account with OAuth. Use when DDNA is not connected or reports an authentication or permission failure.
---

# DDNA Setup

Use this skill when DDNA is not connected yet or reports an authentication failure.

1. Start any DDNA action. The client discovers DDNA's OAuth sign-in and opens the DDNA authorization page. In Claude Code, run `/mcp`, select `ddna`, and choose Authenticate.
2. The user signs in to their existing DDNA account, picks the workspace that records the connection, and checks the permissions to grant. Read is always included; the user decides the rest.
3. Retry the original DDNA action. Never ask for tokens, passwords, environment variables, or configuration edits.
4. If an action is refused for a missing permission, name the permission it needs (Assist and generate, Edit and collaborate, or Decide and publish) and tell the user they can reconnect to grant it. Do not retry.
5. If access is denied for another reason, call `ddna_connection_status` once and explain whether reconnection, another workspace, or a DDNA role change is needed.

DDNA checks workspace membership and project permissions on every call. OAuth connections never receive administrative access.
