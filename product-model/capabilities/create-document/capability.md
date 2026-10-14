---
availability:
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-editor.php#WP_Document_Revisions_Admin_Editor.make_private
- kind: code
  role: implementation
  target: src/admin/wp-document-revisions.js
- kind: doc
  role: intent
  target: docs/frequently-asked-questions.md
---

# Create document

A person adds a new document from Add Document: a title, a description, its first file and a revision summary. A new document is private unless its creator chooses another visibility.
