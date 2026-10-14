---
kind: alternative
routes:
  web: Web
steps:
- text: The Author opens All Documents on a site with no documents yet
  kind: actor
  actor: author
  entities:
  - entity: document
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::documents-list
- text: No document exists in any status
  kind: condition
  entities:
  - entity: document
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::documents-list
- text: The Product shows a welcome notice with a link to add the first document and to read the documentation
  kind: product
  actor: author
  entities:
  - entity: document
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::documents-list
---

# Prompt to add the first document

## Trigger

A new site starts using WP Document Revisions.

## Outcome

The Author is invited to add the first document instead of facing an empty table; the notice is not shown while searching or filtering, or to people who cannot create documents.
