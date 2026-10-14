---
appliesTo:
- type: entity
  id: document
  effect: creates
  facts:
  - Visibility
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-editor.php#WP_Document_Revisions_Admin_Editor.make_private
---

# A new document is private unless its creator chooses otherwise

Add Document starts with Private visibility, so a document is only reachable by the team until someone decides to share it.
