---
kind: alternative
routes:
  web: Web
steps:
- text: The Author chooses Fix beside an address warning of their document
  kind: actor
  actor: author
  entities:
  - entity: document
    effect: reads
    facts:
    - Permanent link
  contexts:
    web:
      place: web::signed-in::validate-structure
- text: The Product stores the document's correct permanent link
  kind: product
  actor: author
  entities:
  - entity: document
    effect: changes
    facts:
    - Permanent link
  contexts:
    web:
      place: web::signed-in::validate-structure
---

# Repair a stored address

## Trigger

A document's stored address no longer matches its permanent link.

## Outcome

The warning is gone.
