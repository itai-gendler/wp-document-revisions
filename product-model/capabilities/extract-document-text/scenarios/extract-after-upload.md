---
kind: unattended
routes:
  web: Web
steps:
- text: A new file was uploaded to a document that does not skip text extraction
  kind: condition
  unattended: true
  entities:
  - entity: revision
    effect: reads
    facts:
    - File
  - entity: document
    effect: reads
    facts:
    - Skip text extraction
  contexts:
    web:
      place: web::signed-in
- text: The Product takes the plain text out of the file, about ten seconds later, and keeps it with the revision
  kind: product
  entities:
  - entity: revision
    effect: changes
    facts:
    - Extracted text
  contexts:
    web:
      place: web::signed-in
---

# Extract the text of a new file

## Trigger

A new version of a document is uploaded.

## Outcome

The revision has its text, ready for an AI summary and other uses.

## Edge cases

- A file of a type no extractor reads gets no text.
