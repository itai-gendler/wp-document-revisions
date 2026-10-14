---
kind: edge
routes:
  web: Web
steps:
- text: The Author looks at a problem where the file of their document cannot be found
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
- text: The Product offers no Fix and answers that the problem cannot be fixed automatically if asked
  kind: product
  actor: author
  entities: []
  contexts:
    web:
      place: web::signed-in::validate-structure
---

# A problem that cannot be fixed automatically

## Trigger

The stored file is gone.

## Outcome

The Author resolves it by uploading a new version or trashing the document.
