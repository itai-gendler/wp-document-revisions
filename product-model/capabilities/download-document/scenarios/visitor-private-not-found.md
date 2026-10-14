---
kind: validation
routes:
  web: Web
steps:
- text: The Visitor opens the permanent link of a private document
  kind: actor
  actor: visitor
  entities:
  - entity: document
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::document-file
- text: The Product answers that the page was not found
  kind: product
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::public::document-file
---

# A visitor finds no private document

## Trigger

A link to a private document reaches someone who is not signed in.

## Outcome

No file is served, and the answer does not tell whether the document exists.
