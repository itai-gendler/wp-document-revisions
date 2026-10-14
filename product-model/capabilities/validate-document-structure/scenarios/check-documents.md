---
kind: primary
routes:
  web: Web
steps:
- text: The Contributor opens Validate Structure
  kind: actor
  actor: contributor
  entities: []
  contexts:
    web:
      place: web::signed-in::validate-structure
- text: The Product lists each problem found in the documents the Contributor may edit, as an error or a warning, with a Fix where one is possible
  kind: product
  actor: contributor
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
    - File
    - Permanent link
  contexts:
    web:
      place: web::signed-in::validate-structure
---

# Check documents for problems

## Trigger

Someone suspects a document has lost its file.

## Outcome

Every problem is listed with its document; address problems can be shown or hidden.
