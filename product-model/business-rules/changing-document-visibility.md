---
appliesTo:
- type: entity
  id: document
  effect: changes
  facts:
  - Visibility
  - Password
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

# A document's visibility is changed by people who may publish it

Editors and administrators change the visibility of any document; an author changes it for the documents they own. Contributors cannot make a document public, password protected or private.
