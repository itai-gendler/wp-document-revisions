---
kind: alternative
routes:
  web: Web
steps:
- text: The Author sets a future publish date and chooses Schedule
  kind: actor
  actor: author
  entities:
  - entity: document
    effect: reads
    facts:
    - Publish date
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product schedules the document for that date
  kind: product
  actor: author
  entities:
  - entity: document
    effect: changes
    from: Draft
    to: Scheduled
    facts:
    - Publish date
  contexts:
    web:
      place: web::signed-in::document-editor
---

# Schedule a document

## Trigger

The document must not be available before a given date.

## Outcome

"Document scheduled for" the date shows, with a preview link.
