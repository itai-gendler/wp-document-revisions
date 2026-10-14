---
kind: alternative
routes:
  web: Web
steps:
- text: The Visitor opens a site page holding the Latest Documents block
  kind: actor
  actor: visitor
  entities:
  - entity: document
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::site-page
- text: The Product lists the most recently modified documents with how long ago they changed
  kind: product
  actor: visitor
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
    - Last modified
  contexts:
    web:
      place: web::public::site-page
---

# See the latest documents

## Trigger

A site shows what changed lately.

## Outcome

The Visitor sees the latest published documents.
