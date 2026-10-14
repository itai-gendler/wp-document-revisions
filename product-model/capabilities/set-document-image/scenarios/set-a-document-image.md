---
kind: primary
routes:
  web: Web
steps:
- text: The Author chooses Set Document Image, picks an image and presses Update
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
- text: The Product shows the image with the document, kept apart from the document's own files
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

# Set a document image

## Trigger

The document should be recognizable in lists.

## Outcome

Document lists showing thumbnails show the image; without one, a PDF shows the picture of its first page.
