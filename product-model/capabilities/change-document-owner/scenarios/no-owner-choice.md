---
kind: validation
routes:
  web: Web
steps:
- text: The Author opens one of their documents to edit it
  kind: actor
  actor: author
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product offers no Owner box, so the Author cannot give the document away
  kind: product
  actor: author
  entities:
  - entity: document
    effect: reads
    facts:
    - Owner
  contexts:
    web:
      place: web::signed-in::document-editor
---

# No owner choice for authors

## Trigger

An author wants to hand a document over.

## Outcome

The owner is unchanged; an editor or administrator can change it.
