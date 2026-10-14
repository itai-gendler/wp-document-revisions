---
availability:
- place: web::signed-in
domain: documents
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-revisions.php#WP_Document_Revisions_Revisions.get_document_lock
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-editor.php#WP_Document_Revisions_Admin_Editor.lock_notice
- kind: doc
  role: intent
  target: docs/frequently-asked-questions.md
---

# Check out document

Opening a document in the editor checks it out: the person holds its lock, nobody else can change it while they stay on the document, and All Documents shows them as currently editing it. The lock lapses a few minutes after they leave.
