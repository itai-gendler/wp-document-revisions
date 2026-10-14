---
kind: validation
routes:
  web: Web
steps:
- text: The Subscriber opens the permanent link of a private document they do not own
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

# A subscriber cannot download a private document

## Trigger

A member follows a link to a document meant for the team only.

## Outcome

No file is served.
