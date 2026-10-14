---
kind: primary
routes:
  web: Web
steps:
- text: The Author chooses Trash for their published document
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
- text: The Product moves the document to the trash
  kind: product
  actor: author
  entities:
  - entity: document
    effect: changes
    from: Published
    to: Trashed
    facts: []
  contexts:
    web:
      place: web::signed-in::documents-list
---

# Trash a document

## Trigger

A document is obsolete or was added by mistake.

## Outcome

The document is no longer served or listed on the site; its history and files are kept.
