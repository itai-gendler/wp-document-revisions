---
appliesTo:
- type: entity
  id: workflow-state
  effect: creates
permits:
- actors:
  - editor
  - administrator
- unattended: true
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions.php#WP_Document_Revisions.register_ct
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions.php#WP_Document_Revisions.restrict_workflow_state_insert
---

# Workflow states are created only by editors and administrators

Adding a workflow state needs the permission to manage categories, whether on the Workflow States screen or by typing an unknown state on a document; the defaults are created on their own for a new site.
