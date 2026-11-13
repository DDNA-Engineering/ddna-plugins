---
name: ddna-change-control
description: Work with DDNA change control and technical reviews. Covers engineering change proposals, deviations and waivers, the change board, what a release still needs a proposal for, and technical reviews with their criteria and action items. Use when the user asks to raise, edit, submit, or withdraw a change proposal, deviation, or waiver, or to plan, convene, or track a technical review.
---

# DDNA change control and technical reviews

Resolve the project with `ddna_project_list`. Before any change, follow the ddna-making-changes skill. Every write here needs the Decide and publish permission and runs only on the user's request.

## Change proposals

- Read with `ddna_change_control_change_proposals` and `ddna_change_control_change_proposal`.
- `ddna_change_control_uncovered_changes` lists the records changed since the latest release that no submitted or approved proposal covers. Use it to answer "what does the next release still need?"
- `ddna_change_control_release_records` searches the records of a release.
- `ddna_change_control_create_change_proposal` creates a draft and `ddna_change_control_edit_change_proposal` edits it.
- `ddna_change_control_submit_change_proposal` sends it to the change board and freezes the records it covers. It cannot be edited while submitted, so confirm the content with the user first. `ddna_change_control_withdraw_change_proposal` withdraws it.

The board's decision is made by its members in DDNA. No tool decides a proposal for them.

## Deviations and waivers

- Read with `ddna_change_control_variances` and `ddna_change_control_variance`.
- `ddna_change_control_create_variance`, `ddna_change_control_edit_variance`, `ddna_change_control_submit_variance`, and `ddna_change_control_withdraw_variance` follow the same draft, submit, withdraw path as a change proposal.

## The change board

`ddna_change_control_change_board` reads who sits on the board. `ddna_change_control_set_change_board` changes it; run it only when the user names the members.

## Technical reviews

- Read with `ddna_technical_review_technical_reviews` and `ddna_technical_review`. `ddna_technical_review_starting_criteria` gives the usual criteria for a kind of review.
- Plan one with `ddna_technical_review_create_technical_review` and `ddna_technical_review_edit_technical_review`.
- Criteria: `ddna_technical_review_add_review_criterion`, `ddna_technical_review_edit_review_criterion`, and `ddna_technical_review_remove_review_criterion`.
- `ddna_technical_review_convene_technical_review` moves a planned review to in review and fixes the configuration revision under review. It needs the review's chair or a Project Manager.
- Action items: `ddna_technical_review_add_review_action` and `ddna_technical_review_edit_review_action`.
- `ddna_technical_review_cancel_technical_review` cancels a review. `ddna_technical_review_retry_review_gate` retries the plan gate linked to a review that closed successfully.

A closed review can establish a typed baseline. Releasing that baseline is in the ddna-engineering skill, and its sign-offs are made by people in DDNA.
