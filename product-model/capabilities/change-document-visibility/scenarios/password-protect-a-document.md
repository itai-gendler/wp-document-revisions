---
kind: alternative
routes:
  web: Web
steps:
- text: The Author chooses Password protected, enters a password and presses Update
  kind: actor
  actor: author
  entities:
  - entity: document
    effect: reads
    facts:
    - Visibility
    - Password
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product protects the document with that password
  kind: product
  actor: author
  entities:
  - entity: document
    effect: changes
    facts:
    - Visibility
    - Password
    - Last modified
  contexts:
    web:
      place: web::signed-in::document-editor
---

# Password protect a document

## Trigger

The document is for clients or contractors without an account.

## Outcome

People without an account download it after entering the password; its description and image stay out of document lists.
