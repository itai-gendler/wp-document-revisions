---
kind: primary
routes:
  web: Web
steps:
- text: The Author sets the status of their published document to Draft and saves
  kind: actor
  actor: author
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product turns the document back into a draft
  kind: product
  actor: author
  entities:
  - entity: document
    effect: changes
    from: Published
    to: Draft
    facts:
    - Last modified
  contexts:
    web:
      place: web::signed-in::document-editor
---

# Switch a document back to draft

## Trigger

A published document needs more work before people use it.

## Outcome

The document is a draft again, reached only by people who may edit it.
