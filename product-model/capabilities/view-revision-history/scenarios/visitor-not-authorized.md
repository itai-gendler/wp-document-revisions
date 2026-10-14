---
kind: validation
routes:
  web: Web
steps:
- text: The Visitor opens a site page holding a history block
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::public::site-page
- text: The Product shows that the Visitor is not authorized to read this data
  kind: product
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::public::site-page
---

# Visitors see no revision history

## Trigger

A visitor reaches a page listing a document's history.

## Outcome

Nothing of the history is shown.
