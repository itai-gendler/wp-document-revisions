---
kind: primary
routes:
  web: Web
steps:
- text: The Editor deletes a workflow state
  kind: actor
  actor: editor
  entities:
  - entity: workflow-state
    effect: reads
    facts:
    - Name
    - Document count
  contexts:
    web:
      place: web::signed-in::workflow-states
- text: The Product deletes the workflow state and leaves the documents that were in it with none
  kind: product
  actor: editor
  entities:
  - entity: workflow-state
    effect: removes
  - entity: document
    effect: changes
    facts:
    - Workflow state
  contexts:
    web:
      place: web::signed-in::workflow-states
---

# Delete a workflow state

## Trigger

A stage is no longer part of the workflow.

## Outcome

The workflow state is gone from every list and document.
