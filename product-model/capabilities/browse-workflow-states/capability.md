---
availability:
- place: web::signed-in
domain: workflow-states
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions.php#WP_Document_Revisions.register_ct
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-query.php#WP_Document_Revisions_Query.review_count_statuses
---

# Browse workflow states

A person who keeps the workflow states sees them under Documents > Workflow States, with how many documents are in each.
