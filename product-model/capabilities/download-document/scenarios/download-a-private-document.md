---
kind: alternative
routes:
  web: Web
steps:
- text: The Author opens the permanent link of a private document they own
  kind: actor
  actor: author
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::signed-in::document-file
- text: The Product serves the current file and tells browsers and proxies not to keep a copy
  kind: product
  actor: author
  entities:
  - entity: document
    effect: reads
    facts:
    - File
  contexts:
    web:
      place: web::signed-in::document-file
---

# Download a private document

## Trigger

The owner needs the file of their private document.

## Outcome

The Author has the file; it is not kept in shared caches.
