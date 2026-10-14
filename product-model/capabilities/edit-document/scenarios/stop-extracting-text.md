---
kind: alternative
routes:
  web: Web
steps:
- text: The Author checks Skip text extraction for this document and presses Update
  kind: actor
  actor: author
  entities:
  - entity: document
    effect: reads
    facts:
    - Skip text extraction
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product stops taking text from the document's files and clears the text and AI summaries already kept for every revision
  kind: product
  actor: author
  entities:
  - entity: document
    effect: changes
    facts:
    - Skip text extraction
  - entity: revision
    effect: changes
    facts:
    - Extracted text
    - AI summary
  contexts:
    web:
      place: web::signed-in::document-editor
---

# Skip text extraction for a document

## Trigger

The document is sensitive and its contents should not be kept as text.

## Outcome

No text is extracted from its files and no AI summary is made for it until the box is unchecked; extraction then resumes with new uploads.
