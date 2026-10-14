---
availability:
- place: web::signed-in
domain: documents
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-editor.php#WP_Document_Revisions_Admin_Editor.post_author_meta_box
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-editor.php#WP_Document_Revisions_Admin_Editor.meta_cb
---

# Change document owner

An editor or administrator gives a document to another owner, chosen among the people who may edit documents, in the Owner box of the document editor.
