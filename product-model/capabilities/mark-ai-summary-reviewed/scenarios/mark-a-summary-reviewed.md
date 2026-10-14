---
kind: primary
routes:
  web: Web
steps:
- text: The Author reads the AI suggestion in the revision summary and chooses Mark reviewed
  kind: actor
  actor: author
  entities:
  - entity: revision
    effect: reads
    facts:
    - AI summary
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product records the Author as having reviewed the AI summary, and when
  kind: product
  actor: author
  entities:
  - entity: revision
    effect: changes
    facts:
    - AI summary reviewed by
  contexts:
    web:
      place: web::signed-in::document-editor
---

# Mark an AI summary reviewed

## Trigger

The Author has checked what the language model wrote.

## Outcome

The suggestion shows Reviewed for everyone who opens it later.
