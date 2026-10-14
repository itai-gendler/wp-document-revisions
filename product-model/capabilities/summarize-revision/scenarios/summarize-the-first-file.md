---
kind: unattended
routes:
  web: Web
steps:
- text: The text of the first file of a document that is neither private nor password protected has been extracted
  kind: condition
  unattended: true
  entities:
  - entity: revision
    effect: reads
    facts:
    - Extracted text
  - entity: document
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in
- text: The Product asks the language model to summarize the file and keeps the summary with the revision
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

# Summarize a first version

## Trigger

A document gets its first file, or the change is too large to compare.

## Outcome

The revision has a summary of the file itself.
