---
kind: primary
routes:
  web: Web
steps:
- text: The Author publishes their draft document
  kind: actor
  actor: author
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
    - Visibility
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product publishes the document
  kind: product
  actor: author
  entities:
  - entity: document
    effect: changes
    from: Draft
    to: Published
    facts:
    - Publish date
    - Last modified
  contexts:
    web:
      place: web::signed-in::document-editor
---

# Publish a draft

## Trigger

The document is ready.

## Outcome

The document is live at its permanent link, and "Document published" offers its download.
