---
name: ddna-intent
description: Work on a DDNA project's Intent. Covers the Intent questions and interview, the Intent documents and their revisions, tracked edits, comments, guidance notes, registers such as hazards, constraints, and readiness evidence, visuals, trade studies, generation runs, and review and approval. Use when the user asks to answer Intent questions, read or edit an Intent document or register, generate or update Intent, or review, approve, or return one.
---

# DDNA Intent

Resolve the project with `ddna_project_list`. For background, use the ddna-project-knowledge skill first. Before any change, follow the ddna-making-changes skill: proposals first, direct changes only on request, and `project_version` on tools that take it.

## Questions and the interview

- Progress and next questions: `ddna_project_intent_status`, `ddna_project_intent_questions_next`, and `ddna_intent_list_intent_questions` for the full list.
- Interview: `ddna_project_intent_chat_resume` reads the user's private transcript and pending confirmation cards. `ddna_project_intent_chat_message_send` sends one message to DDNA's Intent assistant. The conversation is private to the user.
- Shared answers: `ddna_project_intent_answer_confirm` records an answer in shared project memory, and `ddna_intent_answer_intent_question` saves an answer to one question. Call either only when the user gives or confirms that answer. `ddna_project_intent_question_disposition` marks a question unknown, not applicable, or delegated, when the user says so.
- `ddna_intent_refine_intent_questions` asks DDNA to refine the open questions with AI. `ddna_intent_export_intent_questions_workbook` returns a download link to the questions as an Excel workbook.

## Documents

- `ddna_project_intent_workspace_get` lists the Intent documents and runs. `ddna_project_intent_artifact_get` reads one document and its current revision; `ddna_intent_get_intent_artifact_page` reads a long one in pages.
- History: `ddna_intent_list_intent_revisions`, `ddna_intent_list_intent_artifact_activity`, and `ddna_intent_list_intent_baselines`.
- Tracked edits: draft with `ddna_project_intent_change_set_draft` against the current revision, keeping the editor block ids. Submit with `ddna_project_intent_change_set_submit`. `ddna_intent_list_intent_change_set_versions` lists a change set's versions, and `ddna_intent_abandon_intent_change_set` abandons one on request. Only an assigned reviewer who has stated a decision may use `ddna_project_intent_change_set_decide`. Accepting suggestions makes a new revision; it does not approve the document.
- Comments: `ddna_intent_create_intent_comment`, `ddna_intent_reply_intent_comment`, and `ddna_intent_update_intent_comment_status`.
- `ddna_intent_restore_intent_revision` and `ddna_intent_reopen_intent_artifact_for_editing` change which text is current. Run them only when the user asks for that exact step.

## Guidance notes

`ddna_intent_list_intent_guidance` reads the project's guidance notes. `ddna_intent_create_intent_guidance` saves a note the user wrote. `ddna_intent_propose_intent_guidance` asks DDNA to propose notes with AI, and `ddna_intent_decide_intent_guidance` records the user's decision on one.

## Registers

Intent registers hold the project's lists, such as hazards, constraints, and technology and manufacturing readiness evidence.

- Read with `ddna_intent_register_entries`, `ddna_intent_register_record`, `ddna_intent_register_revisions`, and `ddna_intent_register_readiness_checklist`.
- `ddna_intent_register_save_record` adds or edits an entry. Changing a baselined entry needs a rationale from the user.
- `ddna_intent_register_review` records that the user reviewed and accepted entries at their current revisions. This is how drafted entries become accepted, so call it only on the user's stated decision.
- `ddna_intent_register_retire` retires an entry on request.

## Visuals

`ddna_intent_visual_get_folder` reads a document's visuals. `ddna_intent_visual_generate_visuals`, `ddna_intent_visual_refine_visual`, and `ddna_intent_visual_retry_visuals` start AI generation of images or diagrams; `ddna_intent_visual_cancel_visuals` stops a batch. `ddna_intent_visual_select_visual` records the chosen one and `ddna_intent_visual_edit_diagram` edits a generated diagram. References come from `ddna_intent_visual_reference_options` and are attached or detached with `ddna_intent_visual_attach_reference` and `ddna_intent_visual_detach_reference`.

## Generation, updates, and research

- Read `ddna_project_intent_catalog`, then start `ddna_project_intent_generate` when the user asks. It returns a run; report progress from `ddna_project_intent_run_get`. `ddna_intent_retry_intent_run` retries a failed run.
- `ddna_intent_reflow_intent` brings dependent documents up to date. It needs the user's explicit confirmation when reviewed or approved documents would return to draft.
- Trade studies: `ddna_intent_run_intent_trade_study` starts one and `ddna_intent_revise_intent_trade_proposal` revises its recommendation.
- Research: `ddna_intent_search_intent_web` searches the public web, and `ddna_intent_capture_intent_research` saves one public page as a project source. Both reach outside DDNA and work only when the project has external research turned on. A search saves nothing and costs research usage.
- `ddna_intent_update_intent_settings` edits the project's Intent settings on request.

## Review and approval

- Who reviews and approves: `ddna_team_get_intent_governance` and `ddna_team_get_my_review_cycles`.
- `ddna_intent_submit_intent_artifact` submits the current revision for review and notifies the people whose sign-off is requested.
- `ddna_team_act_on_review_cycle` records the user's own decision on a review cycle. `ddna_intent_review_intent_artifact` records an approver's decision on a document; an approval also accepts the revision's open issues.
- `ddna_intent_override_intent_blocker` records an accepted-risk override with a rationale. It needs a Project Manager or Workspace Manager and the user's explicit risk acceptance.
- `ddna_team_update_intent_governance`, `ddna_team_update_workflow_assignments`, and `ddna_team_restart_review_cycle` change the review rules or restart a cycle. Run them only on request.

Decisions belong to the person. Report what a document still needs; never choose approve or return for the user.
