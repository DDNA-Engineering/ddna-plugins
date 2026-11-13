---
name: ddna-project-admin
description: Set up and administer a DDNA project. Covers project details and status, connected sources such as GitHub, Notion, and Google Drive, source files, evidence, the project team, invitations and access, and archiving or deleting a project. Use when the user asks to rename or archive a project, connect or sync a source, add evidence, or see or change who has access.
---

# DDNA project set-up and team

Resolve the project with `ddna_project_list`. Before any change, follow the ddna-making-changes skill. Team, access, and deletion tools need the Decide and publish permission and the right DDNA role.

## Project details

- `ddna_project_get_project` reads the project and returns its current `project_version`.
- `ddna_project_update_project` edits the name, description, system type, or status. Setting the status to active also makes it the organization's active project, and setting it to archived needs the Decide and publish permission.
- `ddna_project_get_project_electrical_pcb_profile` reads the electrical and circuit board profile. `ddna_project_get_project_lifecycle_artifacts` reads life-cycle artifact readiness.
- `ddna_project_generate_project_build_summary` regenerates the project overview with AI, on request.

## Sources and evidence

- `ddna_project_list_project_sources` lists connected sources. `ddna_project_source_files` and `ddna_project_source_file` read the files DDNA holds.
- `ddna_project_create_project_source` connects a GitHub repository, Notion page, or Google Drive file and imports it right away as project evidence. `ddna_project_sync_project_source` imports it again and starts processing of the refreshed content. Both read from outside DDNA.
- `ddna_project_retry_project_source_file` retries a failed file. `ddna_project_delete_project_source` and `ddna_project_delete_project_source_file` remove a source or a file on request.
- `ddna_project_submit_project_evidence` records a note or a reference to an uploaded document as evidence. Uploading a file itself is done by a person in DDNA.
- `ddna_project_process_project_evidence` and `ddna_project_reextract_project` start requirement extraction with AI. Start them only on request; they are rejected for archived and Intent-enabled projects.
- Connected Notion: `ddna_project_notion_search` finds pages by title and `ddna_project_notion_page` reads one, through the user's own Notion connection. Neither imports anything into the project.

## Team and access

- `ddna_team_get_project_team` lists members, invitations, and access.
- `ddna_team_add_workspace_member_to_project`, `ddna_team_patch_project_team_member`, and `ddna_team_delete_project_team_member` add, change, or remove a member.
- `ddna_team_invite_project_team_member` emails an invitation as Editor or Viewer. `ddna_team_resend_project_invitation` and `ddna_team_revoke_project_invitation` manage it. `ddna_project_invite_project_design_owner` invites a person so they can be assigned as a design owner.

Each of these changes who can see or change the project, and some send email. Before the call, repeat the person's email address and the access level back to the user and get a clear yes. Never pick between people with similar names.

Review and approval rules for Intent are in the ddna-intent skill.

## Archiving and deleting

`ddna_project_delete_project` archives a project by default, which can be reversed by changing its status. With the purge option it permanently deletes the project and its data, which cannot be undone and needs a Project Manager. Use purge only when the user asks for permanent deletion in plain words, names the project, and confirms after you state that it cannot be undone.
