---
name: ddna-dfmea
description: Work with a DDNA project's design failure mode and effects analysis (DFMEA). Covers the project summary, analyses and their worksheets, runs, evidence questions, failure chain corrections, the milestone policy, and exports. Use when the user asks about failure modes, causes, effects, controls, or ratings, or asks to answer a DFMEA question, correct a failure chain, or start or check a DFMEA run.
---

# DDNA DFMEA

Resolve the project with `ddna_project_list`. Before any change, follow the ddna-making-changes skill.

## Reading

1. `ddna_dfmea_get_authority` says whether DFMEA is active for the project. If it is not, say so and stop.
2. `ddna_dfmea_project_summary` gives the project-wide picture. `ddna_dfmea_list_analyses` lists the analyses.
3. `ddna_dfmea_get_analysis` reads one analysis worksheet. `ddna_dfmea_analysis_method_criteria` explains its rating method, so read it before explaining a rating.
4. `ddna_dfmea_requirement_dfmea` lists the failure chains tied to one requirement.
5. `ddna_dfmea_get_run` reads a run's status. `ddna_dfmea_export_revision` returns a download link to a worksheet revision.

Report ratings as DDNA recorded them. Do not rescore a failure chain from general knowledge.

## Answering and correcting

- Evidence questions: `ddna_dfmea_get_evidence_question_options` lists the evidence a question can cite. `ddna_dfmea_answer_evidence_question` records the user's answer with at least one cited source and queues the analysis for regeneration, which uses AI.
- Corrections: `ddna_dfmea_get_failure_chain_correction_options` lists what can be corrected. `ddna_dfmea_correct_failure_chain` saves a person's correction to effects, cause, controls, ratings, linked requirements, or evidence as a new worksheet revision. It needs a rationale; use the user's own.

The answer and the correction are the user's engineering judgment. Draft wording if asked, and save only what the user confirms.

## Runs and scope

- `ddna_dfmea_create_run` starts a run that generates or regenerates a worksheet with AI. `ddna_dfmea_create_analysis` creates an analysis limited to a subsystem, a configuration, or a set of requirements, and queues its generation. Both cost AI usage; start them only when the user asks. The project-wide analysis belongs to DDNA and cannot be created this way.
- `ddna_dfmea_get_lifecycle_policy` reads the milestone policy. `ddna_dfmea_update_lifecycle_policy` changes it on request.
