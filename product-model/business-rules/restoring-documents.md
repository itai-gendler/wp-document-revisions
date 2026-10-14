---
appliesTo:
- type: entity
  id: document
  effect: changes
  from: Trashed
permits:
- actors:
  - editor
  - administrator
- related:
  - verb: owns
    entity: author
- related:
  - verb: owns
    entity: contributor
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions.php#WP_Document_Revisions.add_caps
---

# A trashed document is restored by its owner, an editor or an administrator

Bringing a document back from the trash needs the permission to delete it.
