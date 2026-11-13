---
name: ddna-requirement-ide
description: Review, refine, and close out DDNA requirements through the approval-only Requirement IDE. Use when the user asks to review a requirement for quality or testability, find what a requirement is missing, record evidence or answers, or approve or reject a requirement change proposal.
---

# DDNA Requirement IDE

Use this skill when the user asks to review, close out, refine, or decide a DDNA requirement.

1. Find the requirement with `ddna_requirement_list`, asking for the smallest useful page. Check `ddna_connection_status` only when sign-in, workspace, or permissions are unclear.
2. Read the requirement with `ddna_requirement_get` before any detailed analysis or drafting. It returns the full profile, source references, evidence, and review state.
3. For reviewable field patches or follow-up questions on one requirement, use `ddna_requirement_workbench_assistant`.
4. For multi-turn work, open an approval-only session with `ddna_requirement_ide_session_create` and continue it with `ddna_requirement_ide_message_send`.
5. Record an answer with `ddna_requirement_ide_question_answer` or attach evidence with `ddna_requirement_ide_evidence_record` only when the user supplies or identifies it.
6. Read stored change proposals with `ddna_requirement_change_proposal_list`.
7. Decide a proposal only after the user explicitly chooses approve or reject: `ddna_requirement_ide_proposal_apply` for a Requirement IDE proposal, `ddna_requirement_change_proposal_decide` for a stored change proposal. Never infer the decision.

Every patch and proposal is reviewable. DDNA never applies a change automatically, and a decision needs the user's current approver authority.

Use standards context only when the requirement or the user's request is standards-driven. If DDNA reports a permission error, name the workspace or project role, or the connection permission, that is needed, and stop that action. Do not retry a failed write automatically.
