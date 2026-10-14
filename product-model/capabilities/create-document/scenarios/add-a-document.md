---
kind: primary
routes:
  web: Web
steps:
- text: The Author chooses Add Document, enters a title and a description and uploads the file with Upload New Version
  kind: actor
  actor: author
  entities:
  - entity: document
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Author writes a summary of the change and publishes
  kind: actor
  actor: author
  entities: []
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product creates a private document owned by the Author, with the file as its first revision
  kind: product
  actor: author
  entities:
  - entity: document
    effect: creates
    to: Published
    facts:
    - Title
    - Description
    - File
    - Owner
    - Visibility
    - Slug
    - Permanent link
    - Publish date
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
- text: The Product stores the file in the upload directory under a random name, never the name it was uploaded with
  kind: product
  actor: author
  entities:
  - entity: document-settings
    effect: reads
    facts:
    - Upload directory
  contexts:
    web:
      place: web::signed-in::document-editor
---

# Add a document

## Trigger

The Author has a file the team should keep and work on.

## Outcome

The document is published privately: signed-in people who may read private documents, and the Author, can download it at its permanent link, which shows the Download link and "Document published".

## Edge cases

- A person who may not upload files is warned on Add Document that they will not be able to upload any documents.
