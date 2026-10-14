---
kind: validation
routes:
  web: Web
steps:
- text: The Author types a workflow state that does not exist in Quick Edit of their document
  kind: actor
  actor: author
  entities:
  - entity: workflow-state
    effect: reads
    facts:
    - Name
  - entity: document
    effect: reads
    facts:
    - Workflow state
  contexts:
    web:
      place: web::signed-in::documents-list
- text: The Product refuses with Sorry, you are not allowed to create workflow states
  kind: product
  actor: author
  entities:
  - entity: workflow-state
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::documents-list
---

# An author cannot add a workflow state by typing it

## Trigger

An author tries to invent a new stage.

## Outcome

No workflow state is created; only people who keep the list add them.
