---
kind: validation
routes:
  web: Web
steps:
- text: The Author opens their own document while someone else has it checked out
  kind: actor
  actor: author
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
- text: The Product shows who holds the lock and offers no override
  kind: product
  actor: author
  entities: []
  contexts:
    web:
      place: web::signed-in::document-editor
---

# Authors cannot override a lock

## Trigger

An author finds their document checked out by someone else.

## Outcome

The lock stays with its holder until it lapses or an editor or administrator overrides it.
