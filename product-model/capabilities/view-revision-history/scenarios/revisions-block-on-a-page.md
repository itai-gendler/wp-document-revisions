---
kind: alternative
routes:
  web: Web
steps:
- text: The Contributor opens a site page holding the history block of a document they may read
  kind: actor
  actor: contributor
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::signed-in::site-page
- text: The Product lists the document's latest revisions with how long ago and by whom each was saved, and their summaries when the block shows them
  kind: product
  actor: contributor
  entities:
  - entity: revision
    effect: reads
    facts:
    - Number
    - Saved by
    - Saved at
    - Summary
  - entity: document
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::site-page
---

# See revisions on a site page

## Trigger

A team publishes a document's history on an intranet page.

## Outcome

Each listed revision links to its own file.

## Edge cases

- A document that needs a password shows no history until the password has been entered.
