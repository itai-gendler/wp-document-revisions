---
availability:
- place: web::signed-in
domain: documents
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-settings.php#WP_Document_Revisions_Admin_Settings.delete_attachments_with_document
---

# Delete document permanently

A person deletes a document in the trash for good: the document, all its revisions and the files of every version are removed.
