---
appliesTo:
- type: entity
  id: document-lock
  effect: changes
  facts:
  - Holder
permits:
- actors:
  - editor
  - administrator
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-revisions.php#WP_Document_Revisions_Revisions.override_lock
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions.php#WP_Document_Revisions.add_caps
---

# Another person's lock is overridden only by editors and administrators

Overriding needs the permission to override document locks as well as to edit the document; everyone else waits for the lock to lapse.
