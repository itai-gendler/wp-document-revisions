---
kind: primary
routes:
  web: Web
steps:
- text: The Author opens their document to edit it
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
- text: The Product gives the Author the lock and says the file is checked out to them for as long as they remain on the page
  kind: product
  actor: author
  entities:
  - entity: document-lock
    effect: creates
    facts:
    - Holder
    - Last active
  contexts:
    web:
      place: web::signed-in::document-editor
---

# Check out a document

## Trigger

The Author is about to work on the document.

## Outcome

Nobody else can change the document meanwhile; All Documents shows the Author as currently editing it.

## Edge cases

- While the Author stays on the page, even minimized, the lock is renewed about every minute.
