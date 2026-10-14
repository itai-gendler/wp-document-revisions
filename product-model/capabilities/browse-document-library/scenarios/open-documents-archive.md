---
kind: alternative
routes:
  web: Web
steps:
- text: The Visitor opens the documents archive
  kind: actor
  actor: visitor
  entities:
  - entity: document
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::documents-archive
- text: The Product lists the published documents, newest first, each linking to its file
  kind: product
  actor: visitor
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
    - Publish date
  contexts:
    web:
      place: web::public::documents-archive
---

# Open the documents archive

## Trigger

Someone goes to the documents address of the site.

## Outcome

The Visitor sees every published document they may read.
