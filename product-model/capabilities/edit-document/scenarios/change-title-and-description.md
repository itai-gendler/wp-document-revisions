---
kind: primary
routes:
  web: Web
steps:
- text: The Author changes the title and the description, describes the change and presses Update
  kind: actor
  actor: author
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
    - Description
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product saves the document and records the change as a new revision
  kind: product
  actor: author
  entities:
  - entity: document
    effect: changes
    facts:
    - Title
    - Description
    - Last modified
  - entity: revision
    effect: creates
    facts:
    - Number
    - File
    - Saved by
    - Saved at
    - Summary
  contexts:
    web:
      place: web::signed-in::document-editor
---

# Change the title and description

## Trigger

The document's name or summary for readers is out of date.

## Outcome

The new title and description show wherever the document is listed, and the revision log has a new entry with the Author's summary.
