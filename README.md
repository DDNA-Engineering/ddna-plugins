# DDNA plugins

Connect your AI assistant to [DDNA](https://www.defense-dna.com) (Defense DNA) and work on your engineering projects from Claude, ChatGPT, or Codex: review requirements, shape Project Intent documents, run engineering skills, and collaborate through project Git tasks and issues.

You sign in with your **existing DDNA account**. The assistant can only reach the projects your DDNA workspace and project roles allow, and only with the permissions you choose when you connect. You never paste tokens or passwords into the assistant.

The plugin connects to DDNA's hosted MCP server:

```
https://app.defense-dna.com/api/v1/mcp
```

## Install

### Claude (claude.ai, desktop, mobile)

1. Open **Settings → Connectors** and choose **Add custom connector**.
2. Enter the server URL above and choose **Connect**.
3. Sign in to DDNA, pick your workspace, and check the permissions to grant.

On Team and Enterprise plans an organization owner adds the connector first; each member then connects with their own DDNA account.

### Claude Code

```
/plugin marketplace add DDNA-Engineering/ddna-plugins
/plugin install ddna@ddna
```

Then run `/mcp`, select `ddna`, and choose **Authenticate** to sign in to DDNA.

### Codex

```
codex plugin marketplace add DDNA-Engineering/ddna-plugins
codex plugin add ddna@ddna
```

Codex opens the DDNA sign-in page when you install.

### ChatGPT

DDNA is being submitted to the ChatGPT plugin directory. Until it is listed, a workspace admin can add it as a custom connector using the server URL above.

## Permissions

When you connect, DDNA's consent page lists every permission. The ones your assistant asked for start checked; you can add or remove any of them. DDNA grants exactly what you check.

| Permission | Lets the assistant |
| --- | --- |
| Read (always on) | Read projects, requirements, Intent, and project Git; run engineering previews. |
| Assist and generate | Draft requirement proposals, continue Intent conversations, and run Intent generation. |
| Edit and collaborate | Record answers and evidence, draft tracked Intent edits, and create, comment on, close, or reopen project Git tasks and issues. |
| Decide and publish | Approve or reject proposals and gates, and request project Git publication, when you explicitly ask and your DDNA role permits it. |
| Stay connected | Renew access for up to 90 days without signing in again. Without it, the connection lasts one hour. |

To change permissions, disconnect the assistant in DDNA and connect again. You can see and revoke every connection in DDNA.

## What's in this repo

- `plugins/ddna/`: the DDNA plugin. Claude Code reads `.claude-plugin/plugin.json` and `.mcp.json`; Codex and ChatGPT read `plugin.json` and `mcp.json`. Both use the same skills.
- `.claude-plugin/marketplace.json`: the Claude Code marketplace.
- `.agents/plugins/marketplace.json`: the Codex marketplace.

## Links

- Privacy policy: https://www.defense-dna.com/privacy
- Terms of service: https://www.defense-dna.com/terms
- Support: https://www.defense-dna.com/support

## License

Apache-2.0. See [LICENSE](LICENSE).
