---
appliesTo:
- type: entity
  id: document
  effect: changes
  facts:
  - Owner
permits:
- actors:
  - editor
  - administrator
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-editor.php#WP_Document_Revisions_Admin_Editor.meta_cb
---

# A document's owner is changed only by editors and administrators

Giving a document to another owner needs the permission to edit other people's documents; the owner is chosen among the people who may edit documents.
