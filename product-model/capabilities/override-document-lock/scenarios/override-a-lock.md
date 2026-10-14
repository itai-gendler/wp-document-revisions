---
kind: primary
routes:
  web: Web
steps:
- text: The Editor chooses override the lock on a checked-out document
  kind: actor
  actor: editor
  entities:
  - entity: document-lock
    effect: reads
    facts:
    - Holder
  - entity: document
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product gives the lock to the Editor
  kind: product
  actor: editor
  entities:
  - entity: document-lock
    effect: changes
    facts:
    - Holder
    - Last active
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product emails the previous holder that the Editor has overridden their lock on the document and their changes will be lost
  kind: product
  actor: editor
  entities:
  - entity: account
    effect: reads
    facts:
    - Email
    - Display name
  - entity: document
    effect: reads
    facts:
    - Title
    - Permanent link
  contexts:
    web:
      place: web::signed-in::document-editor
---

# Override a lock

## Trigger

Someone left a document checked out and the Editor must change it.

## Outcome

The Editor holds the lock and can upload; the previous holder's page tells them the lock was overridden and reloads.
