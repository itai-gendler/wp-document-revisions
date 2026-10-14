---
kind: validation
routes:
  web: Web
steps:
- text: The Subscriber opens a site page previewing a private document
  kind: actor
  actor: subscriber
  entities:
  - entity: document
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::site-page
- text: The Product shows that the Subscriber is not authorized to read this document
  kind: product
  actor: subscriber
  entities:
  - entity: document
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::site-page
---

# No preview for a reader who may not read the document

## Trigger

A preview of a team-only document is on a page anyone can open.

## Outcome

Nothing of the file is shown.
