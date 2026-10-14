---
appliesTo:
- type: entity
  id: revision
  effect: reads
permits:
- actors:
  - contributor
  - author
  - editor
  - administrator
  - operator
- unattended: true
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions.php#WP_Document_Revisions.add_caps
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-file-handler.php#WP_Document_Revisions_File_Handler.serve_document_auth
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-front-end.php#WP_Document_Revisions_Front_End.revisions_shortcode
---

# Earlier revisions are read only by contributors, authors, editors and administrators

Reading a document's earlier revisions, their files, summaries and history, needs the permission to read revisions, and only for documents the person may read. Subscribers and visitors get the current version only. The Product reads them itself to extract text and summarize changes, as does an operator's command.
