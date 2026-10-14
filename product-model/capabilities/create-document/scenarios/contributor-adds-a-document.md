---
kind: alternative
routes:
  web: Web
steps:
- text: The Contributor chooses Add Document, enters a title and a description and chooses Save Draft
  kind: actor
  actor: contributor
  entities:
  - entity: document
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product creates the document as a draft owned by the Contributor
  kind: product
  actor: contributor
  entities:
  - entity: document
    effect: creates
    to: Draft
    facts:
    - Title
    - Description
    - Owner
    - Visibility
    - Slug
    - Permanent link
    - Skip text extraction
    - Do not pre-fill
    - Last modified
  contexts:
    web:
      place: web::signed-in::document-editor
---

# A contributor adds a document

## Trigger

A contributor starts a document for someone else to complete and publish.

## Outcome

The draft has no file: contributors may not upload files, so someone who may adds it before the document is published.
