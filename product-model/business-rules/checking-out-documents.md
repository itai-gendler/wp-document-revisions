---
appliesTo:
- type: entity
  id: document-lock
  effect: creates
permits:
- actors:
  - editor
  - administrator
- related:
  - verb: holds
    entity: document
  - verb: owns
    entity: author
- related:
  - verb: holds
    entity: document
  - verb: owns
    entity: contributor
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-revisions.php#WP_Document_Revisions_Revisions.get_document_lock
---

# A document is checked out by people who may edit it

Opening a document in the editor takes its lock for editors and administrators on any document, and for owners on their own.
