---
kind: alternative
routes:
  web: Web
steps:
- text: The Subscriber opens a site page previewing a document whose file is neither a PDF nor an image
  kind: actor
  actor: subscriber
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::signed-in::site-page
- text: The Product says the file type cannot be previewed inline and offers a download link instead
  kind: product
  actor: subscriber
  entities:
  - entity: document
    effect: reads
    facts:
    - File
  contexts:
    web:
      place: web::signed-in::site-page
---

# Preview a file that cannot be shown inline

## Trigger

The previewed document is, for example, a spreadsheet.

## Outcome

The Subscriber can still download it; images are shown directly.
