---
appliesTo:
- type: entity
  id: document
  effect: changes
  from: Published
  to: Draft
permits:
- actors:
  - editor
  - administrator
- related:
  - verb: owns
    entity: author
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions.php#WP_Document_Revisions.add_caps
---

# A published document is turned back into a draft by its owning author, an editor or an administrator

Changing a published document needs the permission to edit published documents, which contributors do not have.
