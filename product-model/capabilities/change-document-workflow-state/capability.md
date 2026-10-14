---
availability:
- place: web::signed-in
domain: documents
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-editor.php#WP_Document_Revisions_Admin_Editor.workflow_state_save
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-notifications.php#WP_Document_Revisions_Notifications.notify_workflow_state_change
- kind: doc
  role: intent
  target: docs/notifications.md
---

# Change document workflow state

A person moves a document to another workflow state, or to none, from its editor or with Quick Edit or Bulk Edit in All Documents. When notifications are on, the people to be told get an email.
