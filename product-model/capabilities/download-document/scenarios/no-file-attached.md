---
kind: edge
routes:
  web: Web
steps:
- text: The Subscriber opens the permanent link of a published document that has no file, or whose file is gone from storage
  kind: actor
  actor: subscriber
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::signed-in::document-file
- text: The Product answers not found, saying No document file is attached when there is none
  kind: product
  actor: subscriber
  entities:
  - entity: document
    effect: reads
    facts:
    - File
  contexts:
    web:
      place: web::signed-in::document-file
---

# A document without a file

## Trigger

The document lost its file or never had one.

## Outcome

Nothing is served; Validate Structure reports the document.
