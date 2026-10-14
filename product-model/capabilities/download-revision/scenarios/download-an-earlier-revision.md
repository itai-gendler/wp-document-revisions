---
kind: primary
routes:
  web: Web
steps:
- text: The Author chooses the time of an earlier revision in the revision log
  kind: actor
  actor: author
  entities:
  - entity: revision
    effect: reads
    facts:
    - Number
    - Saved at
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product serves the file that revision held, named after the document with -revision- and its number
  kind: product
  actor: author
  entities:
  - entity: revision
    effect: reads
    facts:
    - File
  - entity: document
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::signed-in::document-file
---

# Download an earlier revision

## Trigger

The Author wants to compare with what the document said before.

## Outcome

The Author has the earlier file; the current version is unchanged.
