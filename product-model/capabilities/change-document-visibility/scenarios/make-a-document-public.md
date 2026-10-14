---
kind: primary
routes:
  web: Web
steps:
- text: The Author changes the visibility of their private document to Public and presses Update
  kind: actor
  actor: author
  entities:
  - entity: document
    effect: reads
    facts:
    - Visibility
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product makes the document public at its permanent link
  kind: product
  actor: author
  entities:
  - entity: document
    effect: changes
    facts:
    - Visibility
    - Last modified
  contexts:
    web:
      place: web::signed-in::document-editor
---

# Make a document public

## Trigger

The document is ready to share with everyone.

## Outcome

Anyone with the permanent link can download it, and it appears in public document lists.
