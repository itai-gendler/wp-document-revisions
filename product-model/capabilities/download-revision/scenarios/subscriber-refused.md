---
kind: validation
routes:
  web: Web
steps:
- text: The Subscriber opens the address of an earlier version of a published document
  kind: actor
  actor: subscriber
  entities:
  - entity: document
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::document-file
- text: The Product refuses with You are not authorized to access that file
  kind: product
  actor: subscriber
  entities: []
  contexts:
    web:
      place: web::signed-in::document-file
---

# A subscriber cannot download an earlier version

## Trigger

A member without access to earlier versions follows such a link.

## Outcome

No file is served; the document's permanent link still serves the current file.
