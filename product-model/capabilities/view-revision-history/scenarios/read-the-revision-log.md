---
kind: primary
routes:
  web: Web
steps:
- text: The Author opens the document to edit it
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
- text: The Product shows the revision log, newest first, with how long ago each revision was saved, who saved it and its summary, each linked to its own file
  kind: product
  actor: author
  entities:
  - entity: revision
    effect: reads
    facts:
    - Number
    - Saved by
    - Saved at
    - Summary
    - File
  contexts:
    web:
      place: web::signed-in::document-editor
---

# Read the revision log

## Trigger

The Author wants to know how the document got to where it is.

## Outcome

The whole history is visible at a glance, with an RSS Feed link for following it in a feed reader.
