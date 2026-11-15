---
description: "Ask today's five DDNA Intent questions for a project and save the answers you give."
argument-hint: "[project name]"
---

Ask today's five DDNA Intent questions for the project named in $ARGUMENTS. If no project is named, ask which one.

Follow step 3 of the ddna-getting-started skill:

1. Resolve the project with `ddna_project_list` and read the current `project_version` with `ddna_project_source_files`.
2. Get the questions with `ddna_project_intent_questions_next` and `limit` 5.
3. Ask them one at a time with what DDNA already knows and the example answers.
4. Save each answer with `ddna_intent_answer_intent_question` only after the user gives it. Never answer for the user.
5. End with how many questions are still open.
