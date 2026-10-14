---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor opens a site page holding a Document Library table
  kind: actor
  actor: visitor
  entities:
  - entity: document
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::site-page
- text: The Product lists the published documents with the chosen details, such as title, file type, owner, last modified and a download button
  kind: product
  actor: visitor
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
    - Description
    - File
    - Document image
    - Owner
    - Last modified
  contexts:
    web:
      place: web::public::site-page
---

# Browse a document library

## Trigger

A site offers its public documents in one place.

## Outcome

The Visitor sees the published documents they may read; a download button appears only where the file can be served to them.

## Edge cases

- A password-protected document is listed without its description or image.
- With no matching document the library says No documents found.
