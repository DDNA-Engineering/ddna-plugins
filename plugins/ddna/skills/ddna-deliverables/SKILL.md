---
name: ddna-deliverables
description: Work with a DDNA project's deliverable documents. Covers the system/subsystem specification, interface control document, verification cross-reference matrix, and architecture views description, plus their Word exports, review decisions, document control settings, and release readiness. Use when the user asks to open, check, export, or review a deliverable, or asks whether the deliverables are ready for a release.
---

# DDNA deliverables

Resolve the project with `ddna_project_list`. Before any change, follow the ddna-making-changes skill.

## Reading

- `ddna_deliverable_overview` lists the deliverable documents and their exports.
- `ddna_deliverable_open_document` returns one document for a configuration. For an editor it creates the document if it is missing and brings its tables up to the working version, so it counts as a change; a reader gets the document as it stands.
- `ddna_deliverable_release_readiness` says what each deliverable still needs before a release.
- `ddna_deliverable_views` reads the architecture views as tables. `ddna_deliverable_sss_placements` lists where each requirement sits in the specification. `ddna_deliverable_phases` and `ddna_deliverable_test_methods` list the life-cycle phases and chosen test methods used for verification.
- `ddna_deliverable_templates` lists the workspace's Word templates.

## Exports

- `ddna_deliverable_export` makes a Word file from the working version or from the text frozen with a release, and keeps it in the project's exports. The verification matrix also keeps an Excel workbook.
- `ddna_deliverable_get_run` reads one export's details. `ddna_deliverable_download` returns a download link for a person signed in to DDNA. Give the link to the user.
- Release packages are in the ddna-engineering skill.

## Changing and checking

- `ddna_deliverable_place_requirements` moves requirements between specification paragraphs.
- `ddna_deliverable_check_coherence` compares a document's text with the engineering model and the approved Intent documents using AI, and adds any fixes as tracked suggestions for people to accept or reject. It costs AI usage; run it on request.
- `ddna_deliverable_save_document_control` saves the project's document control settings: organization name, CAGE code, contract number, document numbers, contract data items, proprietary notice, and markings. Use only values the user gives. Never guess a contract number, a CAGE code, or a marking.

## Review

`ddna_deliverable_review_document` records a designated reviewer's or approver's decision: approved, or changes requested with a note. DDNA rejects an approval while suggestions are waiting, and any decision if the text changed since it was read. Record it only after the user states the decision.
