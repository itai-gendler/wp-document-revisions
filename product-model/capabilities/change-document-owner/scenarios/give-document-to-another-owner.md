---
kind: primary
routes:
  web: Web
steps:
- text: The Editor picks another person as Document Owner and presses Update
  kind: actor
  actor: editor
  entities:
  - entity: document
    effect: reads
    facts:
    - Owner
  - entity: account
    effect: reads
    facts:
    - Display name
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product makes that person the owner of the document
  kind: product
  actor: editor
  entities:
  - entity: document
    effect: changes
    facts:
    - Owner
    - Last modified
  contexts:
    web:
      place: web::signed-in::document-editor
---

# Give a document to another owner

## Trigger

Responsibility for a document moves to someone else.

## Outcome

The new owner is shown in All Documents, receives the document's notifications and, as owner, may work on it with their own role.
