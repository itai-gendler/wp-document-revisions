---
kind: primary
routes:
  web: Web
steps:
- text: The Editor enters the name and description of a new workflow state and adds it
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
- text: The Product creates the workflow state
  kind: product
  actor: editor
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

# Add a workflow state

## Trigger

The team's workflow has a stage the list lacks, such as Approved.

## Outcome

Documents can be put in the new workflow state from their editor and from All Documents.
