---
kind: alternative
routes:
  web: Web
steps:
- text: The Author enters a title, uploads the file and chooses Save Draft
  kind: actor
  actor: author
  entities: []
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product creates the document as a draft owned by the Author
  kind: product
  actor: author
  entities:
  - entity: document
    effect: creates
    to: Draft
    facts:
    - Title
    - Description
    - File
    - Owner
    - Visibility
    - Slug
    - Permanent link
    - Skip text extraction
    - Do not pre-fill
    - Last modified
  - entity: revision
    effect: creates
    facts:
    - Number
    - File
    - Saved by
    - Saved at
    - Summary
    with: document
  contexts:
    web:
      place: web::signed-in::document-editor
---

# Save a document as a draft

## Trigger

The document is not ready to share.

## Outcome

The draft is reachable only by people who may edit it, through a preview link rather than a permanent link.
