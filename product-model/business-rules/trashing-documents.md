---
appliesTo:
- type: entity
  id: document
  effect: changes
  to: Trashed
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
  when:
  - state: Draft
- related:
  - verb: owns
    entity: contributor
  when:
  - state: Pending Review
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions.php#WP_Document_Revisions.add_caps
---

# A document is trashed by its owner, an editor or an administrator

Editors and administrators trash any document and authors the documents they own; contributors trash their own only before they are published.
