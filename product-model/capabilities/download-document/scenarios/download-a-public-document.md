---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor opens the permanent link of a public document
  kind: actor
  actor: visitor
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::public::document-file
- text: The Product serves the document's current file under the document's name and extension
  kind: product
  actor: visitor
  entities:
  - entity: document
    effect: reads
    facts:
    - File
  contexts:
    web:
      place: web::public::document-file
---

# Download a public document

## Trigger

Someone was given the link to a published document.

## Outcome

The Visitor has the latest version of the file, without signing in.
