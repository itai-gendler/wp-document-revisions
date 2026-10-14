---
kind: alternative
routes:
  web: Web
steps:
- text: The Author picks the empty choice as the workflow state and presses Update
  kind: actor
  actor: author
  entities:
  - entity: document
    effect: reads
    facts:
    - Workflow state
  - entity: workflow-state
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product leaves the document in no workflow state
  kind: product
  actor: author
  entities:
  - entity: document
    effect: changes
    facts:
    - Workflow state
    - Last modified
  - entity: workflow-state
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::document-editor
---

# Take a document out of every workflow state

## Trigger

The workflow state no longer applies.

## Outcome

The document has no workflow state.
