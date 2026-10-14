---
kind: alternative
routes:
  web: Web
steps:
- text: The Editor reviews a document pending review and publishes it
  kind: actor
  actor: editor
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
    - File
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product publishes the document
  kind: product
  actor: editor
  entities:
  - entity: document
    effect: changes
    from: Pending Review
    to: Published
    facts:
    - Publish date
    - Last modified
  contexts:
    web:
      place: web::signed-in::document-editor
---

# Publish a document pending review

## Trigger

A contributor submitted a document for review.

## Outcome

The document is published; its contributor can no longer change it.
