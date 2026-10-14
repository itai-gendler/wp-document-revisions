---
kind: alternative
routes:
  web: Web
steps:
- text: The Author adds the title and file, changes visibility to Public and publishes
  kind: actor
  actor: author
  entities: []
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product creates the document as public, so anyone with its permanent link can download it
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
---

# Add a public document

## Trigger

The file is meant for clients or the public.

## Outcome

Anyone can download the document at its permanent link, and it appears in the site's document lists.
