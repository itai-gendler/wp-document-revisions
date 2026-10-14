---
kind: alternative
routes:
  web: Web
steps:
- text: The Subscriber opens the documents archive
  kind: actor
  actor: subscriber
  entities:
  - entity: document
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::documents-archive
- text: The Product lists the documents the Subscriber may read, newest first
  kind: product
  actor: subscriber
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
    - Publish date
  contexts:
    web:
      place: web::signed-in::documents-archive
---

# Open the documents archive signed in

## Trigger

A member looks for a document.

## Outcome

The Subscriber sees the published documents and any others their role lets them read.
