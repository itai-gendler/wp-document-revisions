---
kind: alternative
routes:
  web: Web
steps:
- text: The Author opens the admin dashboard
  kind: actor
  actor: author
  entities: []
  contexts:
    web:
      place: web::signed-in::dashboard
- text: The Product shows the five most recently modified documents the Author may see, with how long ago and by whom each was last saved and its status
  kind: product
  actor: author
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
    - Last modified
  - entity: revision
    effect: reads
    facts:
    - Saved by
  contexts:
    web:
      place: web::signed-in::dashboard
---

# See recently revised documents on the dashboard

## Trigger

The Author signs in to see what changed lately.

## Outcome

Each document links to its editor when the Author may edit it, and to its file otherwise.
