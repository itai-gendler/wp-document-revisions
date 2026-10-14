---
kind: alternative
routes:
  web: Web
steps:
- text: The Author opens a document whose AI suggestion someone has already reviewed
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
- text: The Product shows the suggestion as Reviewed, with nothing left to mark
  kind: product
  actor: author
  entities:
  - entity: revision
    effect: reads
    facts:
    - AI summary
    - AI summary reviewed by
  contexts:
    web:
      place: web::signed-in::document-editor
---

# A summary already reviewed

## Trigger

A colleague already checked the summary.

## Outcome

The review stays recorded.
