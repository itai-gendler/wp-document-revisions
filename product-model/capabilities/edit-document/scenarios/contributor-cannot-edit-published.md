---
kind: validation
routes:
  web: Web
steps:
- text: The Contributor tries to open their document after it was published
  kind: actor
  actor: contributor
  entities:
  - entity: document
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product refuses to open it for editing
  kind: product
  actor: contributor
  entities: []
  contexts:
    web:
      place: web::signed-in::document-editor
---

# A contributor cannot change a published document

## Trigger

A contributor wants to change a document of theirs that an editor has published.

## Outcome

The document is unchanged; contributors edit their documents only while they are drafts or pending review.
