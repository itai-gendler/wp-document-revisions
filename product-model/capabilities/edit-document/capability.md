---
availability:
- place: web::signed-in
domain: documents
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-editor.php#WP_Document_Revisions_Admin_Editor.save_document
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-text-extraction-opt-out.php#WP_Document_Revisions_Text_Extraction_Opt_Out.save
---

# Edit document

A person changes a document's own details in the document editor and presses Update: its title and description, and whether text is extracted from its files and AI suggestions pre-fill its revision summary. A change of title or description is kept as a new revision.
