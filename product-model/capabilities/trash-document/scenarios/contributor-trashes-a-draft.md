---
kind: alternative
routes:
  web: Web
steps:
- text: The Contributor chooses Trash for their draft document
  kind: actor
  actor: contributor
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::signed-in::documents-list
- text: The Product moves the draft to the trash
  kind: product
  actor: contributor
  entities:
  - entity: document
    effect: changes
    from: Draft
    to: Trashed
    facts: []
  contexts:
    web:
      place: web::signed-in::documents-list
---

# A contributor trashes a draft

## Trigger

The Contributor abandons a document.

## Outcome

The draft is in the trash; contributors cannot trash documents once they are published.
