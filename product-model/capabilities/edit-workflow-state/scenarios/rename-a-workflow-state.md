---
kind: primary
routes:
  web: Web
steps:
- text: The Editor changes the name and description of a workflow state and saves
  kind: actor
  actor: editor
  entities:
  - entity: workflow-state
    effect: reads
    facts:
    - Name
    - Description
  contexts:
    web:
      place: web::signed-in::workflow-states
- text: The Product saves the workflow state
  kind: product
  actor: editor
  entities:
  - entity: workflow-state
    effect: changes
    facts:
    - Name
    - Description
  contexts:
    web:
      place: web::signed-in::workflow-states
---

# Rename a workflow state

## Trigger

The team renames a stage of its workflow.

## Outcome

Every document in the workflow state shows the new name.
