# DDNA

Connect your AI assistant to [DDNA](https://www.defense-dna.com) (Defense DNA) and work on your engineering projects in plain language.

You sign in with your existing DDNA account. The assistant reaches only the projects your DDNA workspace and project roles allow, with only the permissions you grant when you connect. You never paste a token or password into the assistant.

## What you can do

Anything DDNA's own Project Chat can do in a project, your assistant can do too, with your access.

- **Get oriented.** Ask where a project stands, what is blocking it, what was decided, and what changed since you last looked.
- **Requirements.** Review a requirement for quality and testability, write or edit requirements and their fields, record evidence, and work findings, risks, and assumptions.
- **Intent.** Answer the open Intent questions, read and edit the Intent documents and registers, generate documents and visuals, run trade studies, and review or approve.
- **Engineering model.** Read configurations and baselines, change the System map and leave notes on it, place parts and boards, check mass, power, and cost budgets, import a bill of materials, and release a baseline.
- **Bill of materials.** Read it, compare two of them, see where a part is used, edit lines, and revise a released part.
- **Change control and reviews.** Raise change proposals, deviations, and waivers, and plan and track technical reviews.
- **DFMEA.** Read the failure analysis, answer its evidence questions, and correct a failure chain.
- **Deliverables.** Open the specification, interface control document, and verification matrix, export them to Word, and check release readiness.
- **Tasks and gates.** See your open work across projects, read a project's plan and its Plan of Action and Milestones, create and schedule tasks, and record gate decisions.
- **Stand-ups.** Read your daily stand-up and record your answers.
- **Project set-up and team.** Connect sources, add evidence, and see or change who has access.
- **Issues and releases.** Raise and answer engineering issues, read the project's Git record, and make a release package.

Example requests:

- "Where does my Falcon project stand, and what is blocking it?"
- "Review the Falcon power requirements for testability and tell me what is missing."
- "What is on my plate this week across my DDNA projects?"
- "Which parts are over their mass allocation in the current configuration?"
- "What does the next release still need a change proposal for?"
- "Pin a note on the power board asking who owns the connector choice."

## Install

In Claude Code:

```
/plugin install ddna --marketplace DDNA-Engineering/ddna-plugins
```

Then run `/mcp`, select `ddna`, and choose **Authenticate** to sign in to DDNA. The [repository README](https://github.com/DDNA-Engineering/ddna-plugins#install) covers claude.ai, Codex, and ChatGPT.

## How changes are handled

Your assistant acts as you. It can do what your DDNA role allows and what you permitted when you connected, and nothing more.

- **Proposals come first.** Where DDNA can save a proposal, a draft, or a tracked suggestion for people to review, the assistant uses that.
- **Direct changes happen when you ask for them.** An edit, an approval, a deletion, or a team change is made only when you ask for that exact change. The assistant tells you what changed.
- **DDNA checks that nothing moved.** A change is refused if the project changed after the assistant last read it, so it cannot overwrite someone else's work unseen.
- **Signatures stay with people.** Electronic signatures need your password and a fresh code in DDNA. No assistant can sign for you.
- **Generation costs usage.** Starting generation, extraction, or research starts work in DDNA that uses AI and is charged to your workspace like the same action in the app.

## Permissions

DDNA's consent page lists every permission when you connect. You can add or remove any of them, and DDNA grants exactly what you check.

| Permission | Lets the assistant |
| --- | --- |
| Read (always on) | Read everything you can read in your projects: requirements, Intent, the engineering model and bill of materials, change control, reviews, DFMEA, deliverables, tasks, stand-ups, issues, and project Git. Run previews that save nothing and get download links that open only when you are signed in. |
| Assist and generate | Start AI work in DDNA: Intent documents and visuals, trade studies, requirement extraction and grading, DFMEA runs, engineering generation, web research, and source syncs. |
| Edit and collaborate | Record answers and evidence; write notes and comments; create and edit tasks, issues, requirements and their fields, and project details; draft tracked edits and proposals; export deliverables. |
| Decide and publish | Change the engineering model and bill of materials directly, apply imports, release baselines, raise and submit change proposals and deviations, run technical reviews, edit Intent registers, approve or reject, delete or archive, and change the team and access, when you explicitly ask and your DDNA role permits it. |
| Stay connected | Renew access for up to 90 days without signing in again. Without it, the connection lasts one hour. |

To change permissions, disconnect the assistant in DDNA and connect again. You can see and revoke every connection in DDNA.

## What this plugin contains

This plugin is instructions plus one connection. It contains skills and commands written in Markdown and a pointer to DDNA's hosted MCP server:

```
https://app.defense-dna.com/api/v1/mcp
```

It runs no code on your machine, installs no packages, and has no hooks. The plugin sends requests only to that DDNA server, over HTTPS, after you sign in. Work you start there, such as Intent generation, runs inside DDNA under your account and may research public sources. What the assistant reads from DDNA goes to the assistant you connected, so connect only an assistant your organization allows for that project's data.

## Links

- Support: https://www.defense-dna.com/support
- Privacy policy: https://www.defense-dna.com/privacy
- Terms of service: https://www.defense-dna.com/terms
- Source: https://github.com/DDNA-Engineering/ddna-plugins

## License

Apache-2.0.
