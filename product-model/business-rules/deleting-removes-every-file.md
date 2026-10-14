---
appliesTo:
- type: entity
  id: document
  effect: removes
- type: capability
  id: delete-document-permanently
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-settings.php#WP_Document_Revisions_Admin_Settings.delete_attachments_with_document
---

# Deleting a document permanently removes the files of all its versions

No file of a deleted document is left behind, wherever the upload directory is.
