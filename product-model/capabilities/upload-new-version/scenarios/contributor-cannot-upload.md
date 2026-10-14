---
kind: validation
routes:
  web: Web
steps:
- text: The Contributor opens their draft document to edit it
  kind: actor
  actor: contributor
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product warns that the Contributor may not upload files and will not be able to upload documents, though other details can still be changed
  kind: product
  actor: contributor
  entities:
  - entity: document
    effect: reads
    facts:
    - File
  contexts:
    web:
      place: web::signed-in::document-editor
---

# A contributor cannot upload a file

## Trigger

A contributor wants to attach a file to their document.

## Outcome

The document keeps no new file; someone who may upload files adds it.
