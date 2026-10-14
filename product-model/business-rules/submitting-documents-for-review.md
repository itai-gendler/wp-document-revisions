---
appliesTo:
- type: entity
  id: document
  effect: changes
  to: Pending Review
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

# A draft is submitted for review by its owner, an editor or an administrator

Contributors submit their own drafts because they cannot publish them; authors, editors and administrators may submit too.
