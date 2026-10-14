---
kind: alternative
routes:
  web: Web
steps:
- text: The Author checks Do not pre-fill with AI suggestions and presses Update
  kind: actor
  actor: author
  entities:
  - entity: document
    effect: reads
    facts:
    - Do not pre-fill
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product saves the choice
  kind: product
  actor: author
  entities:
  - entity: document
    effect: changes
    facts:
    - Do not pre-fill
  contexts:
    web:
      place: web::signed-in::document-editor
---

# Stop AI suggestions in the revision summary

## Trigger

The Author prefers to write revision summaries themselves.

## Outcome

The revision summary of this document is no longer pre-filled; text extraction and AI summaries carry on.
