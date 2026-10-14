---
entities:
- entity: workflow-state
  shows:
  - Name
  - Description
  - Document count
  collects:
  - Name
  - Description
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions.php#WP_Document_Revisions.register_ct
---

# Workflow States

Documents > Workflow States: the list of workflow states with how many documents are in each, where they are added, renamed and deleted.
