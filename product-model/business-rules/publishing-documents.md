---
appliesTo:
- type: entity
  id: document
  effect: changes
  to: Published
permits:
- actors:
  - editor
  - administrator
- related:
  - verb: owns
    entity: author
- unattended: true
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions.php#WP_Document_Revisions.add_caps
---

# A document is published by its owning author, an editor or an administrator

Authors publish the documents they own; editors and administrators publish any. A scheduled document is published on its own at its publish date.
