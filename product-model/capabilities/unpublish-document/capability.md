---
availability:
- place: web::signed-in
domain: documents
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-editor.php#WP_Document_Revisions_Admin_Editor.update_messages
---

# Unpublish document

A person who may publish a document takes it back to a draft by changing its status, so it is no longer served at its permanent link to people who may not edit it.
