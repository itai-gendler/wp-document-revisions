---
kind: edge
routes:
  web: Web
steps:
- text: A new file is larger than 20 MB, or reading it fails
  kind: condition
  unattended: true
  entities:
  - entity: revision
    effect: reads
    facts:
    - File
  contexts:
    web:
      place: web::signed-in
- text: The Product keeps no text and does not try the same file again until it is replaced
  kind: product
  entities:
  - entity: revision
    effect: reads
    facts:
    - Extracted text
  contexts:
    web:
      place: web::signed-in
---

# A file whose text cannot be taken

## Trigger

An uploaded file is too large or damaged.

## Outcome

The revision has no text and no AI summary.
