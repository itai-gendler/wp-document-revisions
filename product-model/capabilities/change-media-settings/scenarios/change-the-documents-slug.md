---
kind: alternative
routes:
  web: Web
steps:
- text: The Administrator enters a new slug and saves
  kind: actor
  actor: administrator
  entities:
  - entity: document-settings
    effect: reads
    facts:
    - Documents slug
  contexts:
    web:
      place: web::administration::media-settings
- text: The Product prefixes every document address with the new slug and warns that some previously published addresses may now be broken
  kind: product
  actor: administrator
  entities:
  - entity: document-settings
    effect: changes
    facts:
    - Documents slug
  - entity: document
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::media-settings
---

# Change the documents slug

## Trigger

Documents should live under another address, such as /files/.

## Outcome

Document links and the documents archive use the new slug.
