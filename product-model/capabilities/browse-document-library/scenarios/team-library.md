---
kind: alternative
routes:
  web: Web
steps:
- text: The Editor opens a site page holding a Document Library
  kind: actor
  actor: editor
  entities:
  - entity: document
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::site-page
- text: The Product lists the documents the Editor may read, private ones included, with how many revisions each has
  kind: product
  actor: editor
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
    - File
    - Owner
    - Last modified
  - entity: revision
    effect: reads
    facts:
    - Number
  contexts:
    web:
      place: web::signed-in::site-page
---

# Browse a library as an editor

## Trigger

A team keeps its working documents on an intranet page.

## Outcome

Private and unpublished documents are listed only for people who may read them, and the revision count only for people who may read revisions; a Document List can add an Edit link beside documents the person may edit.
