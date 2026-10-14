---
kind: unattended
routes:
  web: Web
steps:
- text: The holder of a lock has not been on the document for a few minutes
  kind: condition
  unattended: true
  entities:
  - entity: document-lock
    effect: reads
    facts:
    - Last active
  - entity: document
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::documents-list
- text: The Product releases the lock
  kind: product
  entities:
  - entity: document-lock
    effect: removes
  contexts:
    web:
      place: web::signed-in::documents-list
---

# A lock lapses

## Trigger

The holder left the document or lost their connection.

## Outcome

Anyone who may edit the document can check it out; a holder who returns before someone else does carries on without downloading the file again.
