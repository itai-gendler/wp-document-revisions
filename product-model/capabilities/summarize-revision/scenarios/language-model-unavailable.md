---
kind: edge
routes:
  web: Web
steps:
- text: The Author opens a document whose newest file has no AI summary
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
- text: No language model is connected to the site, or AI is turned off for it
  kind: condition
  actor: author
  entities:
  - entity: revision
    effect: reads
    facts:
    - AI summary
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product fills nothing in
  kind: product
  actor: author
  entities: []
  contexts:
    web:
      place: web::signed-in::document-editor
---

# No language model is available

## Trigger

The site has no language model connected.

## Outcome

The Author writes the revision summary themselves; extraction carries on.
