---
kind: alternative
routes:
  web: Web
steps:
- text: The Editor changes the visibility of a public document to Private and presses Update
  kind: actor
  actor: editor
  entities:
  - entity: document
    effect: reads
    facts:
    - Visibility
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product makes the document private
  kind: product
  actor: editor
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

# Make a document private

## Trigger

A document should no longer be public.

## Outcome

Only its owner and people who may read private documents can download it; others are refused.
