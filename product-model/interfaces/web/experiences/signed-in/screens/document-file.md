---
entities:
- entity: document
  shows:
  - Title
  - File
  collects:
  - Password
- entity: revision
  shows:
  - Number
  - File
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-file-handler.php#WP_Document_Revisions_File_Handler.serve_file
---

# Document file

A document's permanent link, or the link of one of its revisions: it serves that file to whoever may read it, or asks for the document's password first. Earlier revisions are reached here by their own links.
