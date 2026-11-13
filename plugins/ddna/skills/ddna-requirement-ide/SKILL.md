---
name: ddna-requirement-ide
description: Review, refine, write, and close out DDNA requirements, and work the findings, risks, assumptions, and guided questions around them. Use when the user asks to review a requirement for quality or testability, find what a requirement is missing, add or edit a requirement or its fields, record evidence or answers, approve or reject a requirement or a change proposal, or work a finding, risk, or assumption.
---

# DDNA requirements

Before any change, follow the ddna-making-changes skill: proposals first, direct changes only on request, and `project_version` on tools that take it.

## Review and refine

1. Find the requirement with `ddna_requirement_list`, asking for the smallest useful page. Check `ddna_connection_status` only when sign-in, workspace, or permissions are unclear.
2. Read the requirement with `ddna_requirement_get` before any detailed analysis or drafting. It returns the full profile, source references, evidence, and review state. `ddna_project_get_requirement_register_history` reads its history.
3. For reviewable field patches or follow-up questions on one requirement, use `ddna_requirement_workbench_assistant`.
4. For multi-turn work, open a session with `ddna_requirement_ide_session_create` and continue it with `ddna_requirement_ide_message_send`.
5. Record an answer with `ddna_requirement_ide_question_answer` or attach evidence with `ddna_requirement_ide_evidence_record` only when the user supplies or identifies it.
6. Propose new wording with `ddna_project_workspace_requirement_proposal`. The requirement stays unchanged until someone applies the proposal. Read stored proposals with `ddna_requirement_change_proposal_list`.
7. Decide a proposal only after the user explicitly chooses approve or reject: `ddna_requirement_ide_proposal_apply` for a Requirement IDE proposal, `ddna_requirement_change_proposal_decide` for a stored change proposal.

## The requirements workspace

- `ddna_project_get_project_formalize_summary` summarizes the workspace. `ddna_project_get_project_needs` lists the project's needs, and `ddna_project_patch_project_need` edits one.
- `ddna_project_create_manual_project_requirement` creates a requirement from the user's wording.
- Fields: `ddna_project_list_project_requirement_field_options` lists allowed values. `ddna_project_patch_project_requirement_profile` edits one requirement's fields and `ddna_project_bulk_patch_requirement_profile` sets one field across several. `ddna_project_list_requirement_profile_proposals` lists suggested values, and `ddna_project_resolve_requirement_profile_proposal_route` accepts or rejects one on the user's decision.
- `ddna_project_review_project_requirement` approves, rejects, or edits one requirement. In Intent-enabled projects, approval and rejection are an approver's sign-off, and an edit returns the requirement to draft. Run it only on the user's stated decision.
- `ddna_project_grade_project_requirement_quality` grades requirement quality with AI, on request.
- `ddna_project_export_project` exports the requirements; formats other than JSON come back as a download link.
- Trace a requirement with `ddna_project_graph_traceability`, `ddna_project_graph_impact`, and `ddna_project_graph_neighbors`.

## Findings, risks, and assumptions

- Findings: `ddna_project_get_project_gaps`, `ddna_project_list_requirement_issues`, and `ddna_project_get_project_gap_activity` read them. `ddna_project_create_requirement_issue` raises one. `ddna_project_resolve_project_gap`, `ddna_project_challenge_project_gap`, and `ddna_project_apply_gap_issue_response` work one on request. `ddna_project_get_project_flow_down_findings` lists flow-down findings.
- Risks: `ddna_project_get_project_risks` reads them. `ddna_project_create_manual_project_risk` adds one, `ddna_project_add_risk_response` and `ddna_project_apply_risk_response` record and apply a response, and `ddna_project_challenge_project_risk` and `ddna_project_review_project_risk` challenge or review one. `ddna_project_synthesize_project_program_risks` generates program risks with AI and replaces earlier unreviewed drafts; `ddna_project_distill_project_risks` recomputes the rule-derived risks without AI.
- Assumptions: `ddna_project_get_project_assumptions`, `ddna_project_challenge_project_assumption`, and `ddna_project_review_project_assumption`.
- `ddna_project_get_project_change_register` searches the project's change register.

## Guided questions

`ddna_project_get_project_interview_prompts` lists them. `ddna_project_answer_project_interview_prompt` records the user's answer and `ddna_project_apply_project_interview_prompt` applies it. `ddna_project_update_project_interview_prompt` edits a question's tracking. `ddna_project_sync_project_interview_prompts` regenerates the questions with AI, and `ddna_project_export_project_interview_prompts_workbook` returns a download link to a workbook.

## Rules

A decision needs the user's current approver authority and their stated choice. Never infer approve or reject.

Use standards context only when the requirement or the user's request is standards-driven. If DDNA reports a permission error, name the workspace or project role, or the connection permission, that is needed, and stop that action. Do not retry a failed write automatically.
