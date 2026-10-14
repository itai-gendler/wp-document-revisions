---
appliesTo:
- type: entity
  id: document-lock
- type: capability
  id: upload-new-version
references:
- kind: doc
  role: intent
  target: docs/frequently-asked-questions.md
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-editor.php#WP_Document_Revisions_Admin_Editor.document_metabox
---

# Only the person holding the lock changes a document

While a document is checked out, everyone else sees who holds it and cannot change it; the lock lasts as long as the holder stays on the document and lapses a few minutes after they leave.
