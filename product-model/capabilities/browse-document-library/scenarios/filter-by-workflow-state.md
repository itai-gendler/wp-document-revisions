---
kind: alternative
routes:
  web: Web
steps:
- text: The Visitor opens a site page whose library lists only documents in the Final workflow state
  kind: actor
  actor: visitor
  entities:
  - entity: workflow-state
    effect: reads
    facts: []
  - entity: document
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::site-page
- text: The Product lists the published documents in that state, with their workflow state
  kind: product
  actor: visitor
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
    - Workflow state
    - File
  - entity: workflow-state
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::public::site-page
---

# A library limited to one workflow state

## Trigger

A site lists only its final documents.

## Outcome

Only documents in the chosen workflow state, or with the chosen categories, are listed.
