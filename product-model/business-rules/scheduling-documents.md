---
appliesTo:
- type: entity
  id: document
  effect: changes
  to: Scheduled
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

# A document is scheduled by its owning author, an editor or an administrator

Scheduling is publishing at a later date and needs the same permission.
