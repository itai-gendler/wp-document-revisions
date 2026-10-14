---
kind: validation
routes:
  web: Web
steps:
- text: The Editor opens a document someone else has checked out
  kind: actor
  actor: editor
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product shows who has prevented other users from making changes and hides Update so nothing can be saved
  kind: product
  actor: editor
  entities:
  - entity: document-lock
    effect: reads
    facts:
    - Holder
  contexts:
    web:
      place: web::signed-in::document-editor
---

# A document is already checked out

## Trigger

Two people want to work on the same document.

## Outcome

The Editor cannot change the document unless they override the lock.
