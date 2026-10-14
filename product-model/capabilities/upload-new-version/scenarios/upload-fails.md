---
kind: edge
routes:
  web: Web
steps:
- text: The Author selects a file of a type the site does not accept for documents, or one larger than the upload limit
  kind: actor
  actor: author
  entities:
  - entity: document
    effect: reads
    facts:
    - File
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product shows Upload failed with the reason and keeps the current version
  kind: product
  actor: author
  entities: []
  contexts:
    web:
      place: web::signed-in::document-editor
---

# An upload fails

## Trigger

The chosen file cannot be accepted.

## Outcome

The document is unchanged and the Author can choose another file.
