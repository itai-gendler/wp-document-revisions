---
kind: validation
routes:
  web: Web
steps:
- text: The Subscriber opens a site page holding a history block
  kind: actor
  actor: subscriber
  entities: []
  contexts:
    web:
      place: web::signed-in::site-page
- text: The Product shows that the Subscriber is not authorized to read this data
  kind: product
  actor: subscriber
  entities: []
  contexts:
    web:
      place: web::signed-in::site-page
---

# Subscribers see no revision history

## Trigger

A member without access to earlier versions reaches a page listing a document's history.

## Outcome

Nothing of the history is shown.
