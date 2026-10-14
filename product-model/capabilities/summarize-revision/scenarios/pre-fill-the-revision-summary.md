---
kind: alternative
routes:
  web: Web
steps:
- text: The Author opens a document whose current version has an AI summary, with the summary field still empty
  kind: actor
  actor: author
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
    - Do not pre-fill
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product fills the revision summary with the AI summary, marked as an AI suggestion to edit before saving, with Dismiss and Mark reviewed
  kind: product
  actor: author
  entities:
  - entity: revision
    effect: reads
    facts:
    - AI summary
  contexts:
    web:
      place: web::signed-in::document-editor
---

# Offer the summary in the revision summary

## Trigger

The Author is about to save the document again.

## Outcome

The Author edits, keeps or dismisses the suggestion; nothing is saved until the Author presses Update, and text already typed is never replaced.
