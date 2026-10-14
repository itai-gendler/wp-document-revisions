---
kind: unattended
routes:
  web: Web
steps:
- text: The publish date of a scheduled document has arrived
  kind: condition
  unattended: true
  entities:
  - entity: document
    effect: reads
    facts:
    - Publish date
  contexts:
    web:
      place: web::signed-in::documents-list
- text: The Product publishes the document
  kind: product
  entities:
  - entity: document
    effect: changes
    from: Scheduled
    to: Published
    facts: []
  contexts:
    web:
      place: web::signed-in::documents-list
---

# A scheduled document goes live

## Trigger

A scheduled document's publish date arrives.

## Outcome

The document is live at its permanent link.
