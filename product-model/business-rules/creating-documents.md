---
appliesTo:
- type: entity
  id: document
  effect: creates
permits:
- actors:
  - contributor
  - author
  - editor
  - administrator
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions.php#WP_Document_Revisions.add_caps
---

# Documents are created by contributors, authors, editors and administrators

Anyone whose role may edit documents adds new ones and becomes their owner; subscribers and visitors cannot.
