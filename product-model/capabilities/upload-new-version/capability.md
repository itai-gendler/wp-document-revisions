---
availability:
- place: web::signed-in
domain: documents
references:
- kind: code
  role: implementation
  target: src/admin/wp-document-revisions.js
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-file-handler.php#WP_Document_Revisions_File_Handler.filename_rewrite
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-notifications.php#WP_Document_Revisions_Notifications.notify_document_saved
- kind: doc
  role: intent
  target: docs/notifications.md
---

# Upload new version

A person checks in a new version of a document: they choose Upload New Version, select the file, optionally describe the change and press Update. The new file becomes the one the permanent link serves, and the previous one stays in the revision log.
