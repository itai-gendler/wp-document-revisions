---
appliesTo:
- type: entity
  id: revision
  facts:
  - File
- type: capability
  id: upload-new-version
references:
- kind: doc
  role: intent
  target: docs/features.md
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-file-handler.php#WP_Document_Revisions_File_Handler.random_file_name
---

# A stored document file never keeps the name it was uploaded with

Each uploaded file is stored under a random name and reached only through the document's addresses, where the document's own name is used.
