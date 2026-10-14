---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor opens a site page previewing a public PDF document
  kind: actor
  actor: visitor
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::public::site-page
- text: The Product embeds the current file in the page with a download link
  kind: product
  actor: visitor
  entities:
  - entity: document
    effect: reads
    facts:
    - File
  contexts:
    web:
      place: web::public::site-page
---

# Preview a PDF

## Trigger

A site shows a policy or report on one of its pages.

## Outcome

The Visitor reads the latest version in place; the preview follows every new version.
