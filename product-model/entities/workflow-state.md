---
domain: workflow-states
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions.php#WP_Document_Revisions.register_ct
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions.php#WP_Document_Revisions.initialize_workflow_states
---

# Workflow state

A stage of the team's document workflow, such as In Progress, Initial Draft, Under Review or Final, that documents are put in to show where they stand.

## Information kept

- **Name** — the state's name
- **Description** — what the state means
- **Document count** — how many documents not in the trash are in it
