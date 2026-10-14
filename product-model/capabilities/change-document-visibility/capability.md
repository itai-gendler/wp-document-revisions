---
availability:
- place: web::signed-in
domain: documents
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-editor.php#WP_Document_Revisions_Admin_Editor.get_help_text
- kind: doc
  role: intent
  target: docs/frequently-asked-questions.md
---

# Change document visibility

A person who may publish a document switches who can download it: Public for anyone with the link, Password protected for those given its password, or Private for signed-in people allowed to read private documents.
