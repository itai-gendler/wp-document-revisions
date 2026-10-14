---
appliesTo:
- type: entity
  id: workflow-state
  effect: removes
permits:
- actors:
  - editor
  - administrator
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions.php#WP_Document_Revisions.register_ct
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions.php#WP_Document_Revisions.restrict_workflow_state_insert
---

# Workflow states are deleted only by editors and administrators

Deleting a workflow state needs the permission to manage categories.
