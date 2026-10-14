---
appliesTo:
- type: entity
  id: document-lock
  facts:
  - Holder
- type: capability
  id: override-document-lock
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-revisions.php#WP_Document_Revisions_Revisions.send_override_notice
---

# Overriding a lock emails the person who held it

The previous holder learns who took the document and that the changes they had not saved will be lost.
