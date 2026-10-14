---
kind: primary
routes:
  web: Web
steps:
- text: The Contributor chooses Submit for Review on their draft document
  kind: actor
  actor: contributor
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product marks the document as pending review
  kind: product
  actor: contributor
  entities:
  - entity: document
    effect: changes
    from: Draft
    to: Pending Review
    facts:
    - Last modified
  contexts:
    web:
      place: web::signed-in::document-editor
---

# Submit a document for review

## Trigger

The Contributor has finished their part of the document.

## Outcome

"Document submitted" shows; the document waits in All Documents for someone who may publish it, and the Contributor can still change it until then.
