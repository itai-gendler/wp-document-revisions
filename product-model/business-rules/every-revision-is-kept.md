---
appliesTo:
- type: entity
  id: revision
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-revisions.php#WP_Document_Revisions_Revisions.possibly_delete_revision
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-query.php#WP_Document_Revisions_Query.manage_document_revisions_limit
---

# A document keeps every revision while it exists

Revisions are kept without limit and other processes cannot delete them; they go only when the document is deleted permanently.
