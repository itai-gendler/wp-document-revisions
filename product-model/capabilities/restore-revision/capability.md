---
availability:
- place: web::signed-in
domain: documents
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-editor.php#WP_Document_Revisions_Admin_Editor.revision_metabox
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-editor.php#WP_Document_Revisions_Admin_Editor.restore_document_attachment_id
---

# Restore revision

A person brings back an earlier revision from the revision log: it is copied as the newest revision, so its file, title and description are current again and no history is lost.
