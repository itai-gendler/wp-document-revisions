---
kind: primary
routes:
  web: Web
steps:
- text: The Author chooses Restore for their document in the trash
  kind: actor
  actor: author
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::signed-in::documents-list
- text: The Product takes the document out of the trash as a draft
  kind: product
  actor: author
  entities:
  - entity: document
    effect: changes
    from: Trashed
    to: Draft
    facts: []
  contexts:
    web:
      place: web::signed-in::documents-list
---

# Restore a trashed document

## Trigger

A document was trashed by mistake.

## Outcome

The document is a draft again with its revisions and files, ready to be published again.
