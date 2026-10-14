---
kind: primary
routes:
  web: Web
steps:
- text: The Editor opens the list of workflow states
  kind: actor
  actor: editor
  entities:
  - entity: workflow-state
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::workflow-states
- text: The Product lists every workflow state with its description and how many documents are in it
  kind: product
  actor: editor
  entities:
  - entity: workflow-state
    effect: reads
    facts:
    - Name
    - Description
    - Document count
  - entity: document
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::workflow-states
---

# See the workflow states

## Trigger

The Editor wants to see how the team's documents are spread across the workflow.

## Outcome

Each count includes drafts, private and pending documents, not only published ones.
