---
kind: alternative
routes:
  web: Web
steps:
- text: The Administrator chooses to remove the year and month from permalinks and saves
  kind: actor
  actor: administrator
  entities:
  - entity: document-settings
    effect: reads
    facts:
    - Date in permalink
  contexts:
    web:
      place: web::administration::media-settings
- text: The Product builds document addresses without the year and month
  kind: product
  actor: administrator
  entities:
  - entity: document-settings
    effect: changes
    facts:
    - Date in permalink
  - entity: document
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::media-settings
---

# Remove the date from document addresses

## Trigger

Shorter document addresses are wanted.

## Outcome

Document addresses leave out /yyyy/mm; addresses with the date still work.
