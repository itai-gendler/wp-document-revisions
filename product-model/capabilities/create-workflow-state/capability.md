---
availability:
- place: web::signed-in
domain: workflow-states
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions.php#WP_Document_Revisions.initialize_workflow_states
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions.php#WP_Document_Revisions.restrict_workflow_state_insert
---

# Create workflow state

A person who keeps the workflow states adds one under Documents > Workflow States. A site starts with four: In Progress, Initial Draft, Under Review and Final.
