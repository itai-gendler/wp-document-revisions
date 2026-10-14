---
availability:
- place: web::signed-in
domain: workflow-states
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions.php#WP_Document_Revisions.register_ct
---

# Delete workflow state

A person who keeps the workflow states deletes one; documents in it are left with no workflow state.
