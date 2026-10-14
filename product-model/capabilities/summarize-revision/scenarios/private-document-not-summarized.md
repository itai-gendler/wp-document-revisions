---
kind: unattended
routes:
  web: Web
steps:
- text: The text of a new version of a private or password-protected document has been extracted
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
- text: The Product sends nothing to the language model
  kind: product
  entities:
  - entity: revision
    effect: reads
    facts:
    - AI summary
  contexts:
    web:
      place: web::signed-in
---

# A private document is not summarized

## Trigger

A confidential document gets a new version.

## Outcome

No summary is made and nothing of the file leaves the site.
