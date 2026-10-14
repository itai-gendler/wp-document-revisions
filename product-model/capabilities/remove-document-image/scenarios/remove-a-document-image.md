---
kind: primary
routes:
  web: Web
steps:
- text: The Author chooses Remove Document Image and presses Update
  kind: actor
  actor: author
  entities:
  - entity: document
    effect: reads
    facts:
    - Document image
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product removes the image from the document
  kind: product
  actor: author
  entities:
  - entity: document
    effect: changes
    facts:
    - Document image
  contexts:
    web:
      place: web::signed-in::document-editor
---

# Remove a document image

## Trigger

The image no longer fits the document.

## Outcome

Lists show the document without an image.
