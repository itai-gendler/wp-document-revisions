---
appliesTo:
- type: entity
  id: workflow-state
  facts:
  - Document count
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-query.php#WP_Document_Revisions_Query.review_count_statuses
---

# A workflow state counts every document that is not in the trash

Drafts, pending, scheduled and private documents count toward a workflow state as well as published ones, so the count shows where all the team's work stands.
