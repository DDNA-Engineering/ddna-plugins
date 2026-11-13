# DDNA

Connect your AI assistant to [DDNA](https://www.defense-dna.com) (Defense DNA) and work on your engineering projects in plain language.

You sign in with your existing DDNA account. The assistant reaches only the projects your DDNA workspace and project roles allow, with only the permissions you grant when you connect. You never paste a token or password into the assistant.

## What you can do

- **Get oriented.** Ask where a project stands, what is blocking it, what was decided, and what changed since you last looked.
- **Requirements.** Review a requirement for quality and testability, find what it is missing, record evidence, and approve or reject change proposals.
- **Intent.** Answer the open Intent questions, read the Intent documents, draft tracked edits for review, and start document generation.
- **Engineering model.** Read configurations and baselines, check mass, power, and cost budgets, propose model and budget changes, and assess what a change would affect.
- **Tasks and gates.** See your open work across projects, read a project's plan and its Plan of Action and Milestones, create and schedule tasks, and record gate decisions.
- **Stand-ups.** Read your daily stand-up and record your answers.
- **Issues and releases.** Raise and answer engineering issues, read the project's Git record, and make a release package.

Example requests:

- "Where does my Falcon project stand, and what is blocking it?"
- "Review the Falcon power requirements for testability and tell me what is missing."
- "What is on my plate this week across my DDNA projects?"
- "Which parts are over their mass allocation in the current configuration?"

## Install

In Claude Code:

```
/plugin install ddna --marketplace DDNA-Engineering/ddna-plugins
```

Then run `/mcp`, select `ddna`, and choose **Authenticate** to sign in to DDNA. The [repository README](https://github.com/DDNA-Engineering/ddna-plugins#install) covers claude.ai, Codex, and ChatGPT.

## How changes are handled

DDNA does not let an assistant change engineering records on its own. Assistants save proposals, drafts, and assessments that people review in DDNA. Approvals, gate decisions, and publication happen only when you ask for them and your DDNA role permits them.

## Permissions

DDNA's consent page lists every permission when you connect. You can add or remove any of them, and DDNA grants exactly what you check.

| Permission | Lets the assistant |
| --- | --- |
| Read (always on) | Read projects, requirements, Intent, the engineering model, budgets, tasks, stand-ups, issues, and project Git; run previews that save nothing. |
| Assist and generate | Draft requirement proposals, continue Intent conversations, and start Intent generation. |
| Edit and collaborate | Record answers and evidence; draft tracked Intent edits; save model, budget, and impact proposals; create and edit tasks, comments, issues, and stand-up answers; make release packages. |
| Decide and publish | Approve or reject proposals and gates, delete or restore tasks, and request project Git publication, when you explicitly ask and your DDNA role permits it. |
| Stay connected | Renew access for up to 90 days without signing in again. Without it, the connection lasts one hour. |

To change permissions, disconnect the assistant in DDNA and connect again. You can see and revoke every connection in DDNA.

## What this plugin contains

This plugin is instructions plus one connection. It contains skills and commands written in Markdown and a pointer to DDNA's hosted MCP server:

```
https://app.defense-dna.com/api/v1/mcp
```

It runs no code on your machine, installs no packages, and has no hooks. The plugin sends requests only to that DDNA server, over HTTPS, after you sign in. Work you start there, such as Intent generation, runs inside DDNA under your account and may research public sources.

## Links

- Support: https://www.defense-dna.com/support
- Privacy policy: https://www.defense-dna.com/privacy
- Terms of service: https://www.defense-dna.com/terms
- Source: https://github.com/DDNA-Engineering/ddna-plugins

## License

Apache-2.0.
