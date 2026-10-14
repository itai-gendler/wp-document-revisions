---
kind: primary
routes:
  web: Web
steps:
- text: The Author chooses Fix beside a problem of their document
  kind: actor
  actor: author
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
    - File
  contexts:
    web:
      place: web::signed-in::validate-structure
- text: The Product repairs the link between the document and its file and reports Processed successfully
  kind: product
  actor: author
  entities:
  - entity: document
    effect: changes
    facts:
    - File
  contexts:
    web:
      place: web::signed-in::validate-structure
---

# Fix a problem

## Trigger

A document lists a file it is not linked to.

## Outcome

The document serves its file again.
