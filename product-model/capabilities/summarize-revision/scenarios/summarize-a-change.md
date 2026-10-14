---
kind: unattended
routes:
  web: Web
steps:
- text: The text of a new version of a document that is neither private nor password protected has been extracted
  kind: condition
  unattended: true
  entities:
  - entity: revision
    effect: reads
    facts:
    - Extracted text
  - entity: document
    effect: reads
    facts:
    - Visibility
  contexts:
    web:
      place: web::signed-in
- text: The Product compares it with the previous version's text and asks the language model for a summary of what changed
  kind: product
  entities:
  - entity: revision
    effect: reads
    facts:
    - Extracted text
  contexts:
    web:
      place: web::signed-in
- text: The Product keeps the summary with the new revision
  kind: product
  entities:
  - entity: revision
    effect: changes
    facts:
    - AI summary
  contexts:
    web:
      place: web::signed-in
---

# Summarize a change

## Trigger

A new version of a document is uploaded.

## Outcome

The revision has a short summary of what changed, ready to be offered in the revision summary.

## Edge cases

- When the text did not change, the summary says there is no textual change and the language model is not asked.
