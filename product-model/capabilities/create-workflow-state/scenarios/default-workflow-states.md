---
kind: unattended
routes:
  web: Web
steps:
- text: A site has no workflow states when the admin is first opened
  kind: condition
  unattended: true
  entities:
  - entity: workflow-state
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::workflow-states
- text: The Product creates In Progress, Initial Draft, Under Review and Final, each with a description
  kind: product
  entities:
  - entity: workflow-state
    effect: creates
    facts:
    - Name
    - Description
    - Document count
  contexts:
    web:
      place: web::signed-in::workflow-states
---

# The default workflow states

## Trigger

WP Document Revisions starts on a site.

## Outcome

The four default workflow states are ready to use.
