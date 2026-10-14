---
availability:
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-file-handler.php#WP_Document_Revisions_File_Handler.serve_document_auth
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-rewrites.php#WP_Document_Revisions_Rewrites.permalink
---

# Download revision

A person who may read earlier revisions opens a revision from the revision log and gets the file that version held, at its own address ending in -revision- and its number.
