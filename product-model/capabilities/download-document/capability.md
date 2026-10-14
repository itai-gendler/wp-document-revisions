---
availability:
- place: web::public
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-file-handler.php#WP_Document_Revisions_File_Handler.serve_file
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-file-handler.php#WP_Document_Revisions_File_Handler.serve_document_auth
- kind: doc
  role: intent
  target: docs/features.md
---

# Download document

A person opens a document's permanent link and gets its current file, which opens in the browser where it can. The same link keeps working, and keeps serving the latest version, however many versions are checked in.
