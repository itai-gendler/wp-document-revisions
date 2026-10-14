---
availability:
- place: web::signed-in
domain: documents
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-list.php
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-settings.php#WP_Document_Revisions_Admin_Settings.dashboard_display
---

# Browse documents

A signed-in person sees the documents they may work on in All Documents, with who owns each, its workflow state, its file, how many revisions it has and who is editing it, and the most recently revised ones on the dashboard.
