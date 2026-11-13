---
name: ddna-standups
description: Read and answer DDNA daily stand-ups, and manage them for a workspace. Use when the user asks for their stand-up, wants to record today's answers, asks what the team reported, or (as a Workspace Manager or project lead) asks to set up or change a stand-up.
---

# DDNA daily stand-ups

## The user's stand-up

1. Read today's stand-up with `ddna_my_standup`. It returns the user's urgent work by project, counts, notes, and the prompts to answer.
2. Record answers with `ddna_standup_answer`. Send the user's own words. Do not write answers for them from task data unless they ask for a draft and then approve it.

## What the team reported

- `ddna_standups` lists the workspace's stand-ups with audience, schedule, sections, notes, prompts, and whether the user can manage them.
- `ddna_standup` reads one stand-up's settings.
- `ddna_standup_responses` lists everyone's answers for one day, when the user is allowed to see them.

## Managing stand-ups

Change a stand-up only when the user asks, and only when `ddna_standups` shows they can manage it.

- `ddna_standup_create` and `ddna_standup_update` set the audience, schedule, delivery, sections, notes, and prompts. Workspace Managers only.
- `ddna_standup_board_set` sets the short notes and the ordered list of headings, lines, and linked DDNA records. Managers and project leads.
- `ddna_standup_delete` removes the stand-up together with its answers. Confirm with the user before calling it. Workspace Managers only.

When DDNA refuses a call for a missing permission or role, stop, name what is missing, and do not retry.
