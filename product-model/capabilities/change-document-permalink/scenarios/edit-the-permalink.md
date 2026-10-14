---
kind: primary
routes:
  web: Web
steps:
- text: The Author chooses Edit beside the permalink, enters a new name and confirms
  kind: actor
  actor: author
  entities:
  - entity: document
    effect: reads
    facts:
    - Slug
    - Permanent link
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product gives the document the new name, made unique, and keeps the old one so its address redirects
  kind: product
  actor: author
  entities:
  - entity: document
    effect: changes
    facts:
    - Slug
    - Permanent link
  contexts:
    web:
      place: web::signed-in::document-editor
---

# Edit the permalink

## Trigger

The document's address should match its new title.

## Outcome

The permanent link uses the new name; the old address redirects to it, except for people who may not see the document.
