---
appliesTo:
- type: entity
  id: document
  effect: removes
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

# A document is deleted permanently by its owner, an editor or an administrator

Deleting for good needs the permission to delete the document, as trashing does.
