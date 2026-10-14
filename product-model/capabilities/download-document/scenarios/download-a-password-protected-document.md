---
kind: alternative
routes:
  web: Web
steps:
- text: The Visitor opens the permanent link of a password-protected document
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
- text: The Product asks for the document's password
  kind: product
  actor: visitor
  entities:
  - entity: document
    effect: reads
    facts:
    - Password
  contexts:
    web:
      place: web::public::document-file
- text: The Visitor enters the password
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::public::document-file
- text: The Product serves the current file
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

# Download a password-protected document

## Trigger

A client was given the link and the password of a document.

## Outcome

The Visitor has the file; without the right password the file is not served.
