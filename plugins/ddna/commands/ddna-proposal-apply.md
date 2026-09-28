---
description: "Approve or reject an existing DDNA Requirement IDE proposal after the user decides."
---

Use DDNA MCP to apply or reject an existing Requirement IDE proposal.

1. Read the proposal through the session resource or Requirement IDE session tools.
2. Confirm the proposal id, target requirement, guardrail status, and user decision.
3. Call `ddna_requirement_ide_proposal_apply` with `approve` or `reject`.
4. Return the trace id and resulting proposal state.
