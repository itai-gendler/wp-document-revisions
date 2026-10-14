---
kind: alternative
routes:
  web: Web
steps:
- text: The Author opens Validate Structure
  kind: actor
  actor: author
  entities: []
  contexts:
    web:
      place: web::signed-in::validate-structure
- text: The Product reports that no invalid documents were found
  kind: product
  actor: author
  entities:
  - entity: document
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::validate-structure
---

# No problems found

## Trigger

All documents are in order.

## Outcome

Nothing needs fixing.
